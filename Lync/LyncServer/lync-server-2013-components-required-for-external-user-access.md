---
title: "Lync Server 2013: componenti necessari per l'accesso degli utenti esterni"
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
ms.openlocfilehash: 05c4b2845f4146c6394712951089750299ce60b7
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="06bbb-102">Componenti necessari per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06bbb-102">Components required for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06bbb-103">_**Ultimo argomento modificato:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="06bbb-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="06bbb-104">La maggior parte dei componenti perimetrali viene distribuita in una rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="06bbb-104">Most Edge components are deployed in a perimeter network.</span></span> <span data-ttu-id="06bbb-105">I componenti riportati di seguito costituiscono la topologia perimetrale della rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="06bbb-105">The following components make up the edge topology of the perimeter network.</span></span> <span data-ttu-id="06bbb-106">Eccetto dove indicato, i componenti fanno parte degli [scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) e si trovano nella rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="06bbb-106">Except where noted, the components are part of the [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and are in the perimeter network.</span></span> <span data-ttu-id="06bbb-107">I componenti perimetrali includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="06bbb-107">Edge components include the following:</span></span>

  - <span data-ttu-id="06bbb-108">server perimetrali</span><span class="sxs-lookup"><span data-stu-id="06bbb-108">Edge Servers</span></span>

  - <span data-ttu-id="06bbb-109">Proxy inversi</span><span class="sxs-lookup"><span data-stu-id="06bbb-109">Reverse proxies</span></span>

  - <span data-ttu-id="06bbb-110">Firewall</span><span class="sxs-lookup"><span data-stu-id="06bbb-110">Firewalls</span></span>

  - <span data-ttu-id="06bbb-111">Direttori (facoltativi e logicamente presenti nella rete interna)</span><span class="sxs-lookup"><span data-stu-id="06bbb-111">Directors (optional, and logically located on the internal network)</span></span>

  - <span data-ttu-id="06bbb-112">Bilanciamento del carico di tipo per topologie perimetrali con scalabilità implementata (bilanciamento del carico DNS o dispositivo di bilanciamento del carico hardware)</span><span class="sxs-lookup"><span data-stu-id="06bbb-112">Load balancing for Scaled Edge Topologies (either DNS load balancing or a hardware load balancer)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="06bbb-p102">Non è possibile usare il bilanciamento del carico DNS in un'interfaccia e il bilanciamento del carico hardware in un'altra. È necessario usare lo stesso tipo di bilanciamento del carico per entrambe le interfacce, in quanto non è supportata una combinazione dei due tipi.</span><span class="sxs-lookup"><span data-stu-id="06bbb-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>

    
    </div>

<div>

## <a name="edge-servers"></a><span data-ttu-id="06bbb-115">server perimetrali</span><span class="sxs-lookup"><span data-stu-id="06bbb-115">Edge Servers</span></span>

<span data-ttu-id="06bbb-116">I server perimetrali inviano e ricevono il traffico di rete per i servizi offerti dalla distribuzione interna da parte di utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="06bbb-116">The Edge Servers send and receive network traffic for the services offered by internal deployment by external users.</span></span> <span data-ttu-id="06bbb-117">Nel server perimetrale vengono eseguiti i servizi seguenti:</span><span class="sxs-lookup"><span data-stu-id="06bbb-117">The Edge Server runs the following services:</span></span>

  - <span data-ttu-id="06bbb-118">**Servizio**     Access Edge Il servizio Access Edge fornisce un singolo punto di connessione attendibile per il traffico SIP (Session Initiation Protocol) in uscita e in ingresso.</span><span class="sxs-lookup"><span data-stu-id="06bbb-118">**Access Edge service**   The Access Edge service provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>

  - <span data-ttu-id="06bbb-119">Servizio Web Conferencing **Edge**     Il servizio Web Conferencing Edge consente agli utenti esterni di partecipare alle riunioni ospitate nella distribuzione interna di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="06bbb-119">**Web Conferencing Edge service**   The Web Conferencing Edge service enables external users to join meetings that are hosted on your internal Lync Server 2013 deployment.</span></span>

  - <span data-ttu-id="06bbb-120">Servizio A/ **V Edge**     Il servizio A/V Edge rende disponibili audio, video, condivisione applicazioni e trasferimento di file per gli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="06bbb-120">**A/V Edge service**   The A/V Edge service makes audio, video, application sharing, and file transfer available to external users.</span></span> <span data-ttu-id="06bbb-121">Gli utenti possono aggiungere audio e video alle riunioni che includono partecipanti esterni e possono comunicare utilizzando audio e/o video direttamente con un utente esterno nelle sessioni punto-punto.</span><span class="sxs-lookup"><span data-stu-id="06bbb-121">Your users can add audio and video to meetings that include external participants, and they can communicate using audio and/or video directly with an external user in point-to-point sessions.</span></span> <span data-ttu-id="06bbb-122">Il servizio A/V Edge offre inoltre il supporto per la condivisione desktop e il trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="06bbb-122">The A/V Edge service also provides support for desktop sharing and file transfer.</span></span>

  - <span data-ttu-id="06bbb-123">**Servizio**     proxy XMPP Il servizio proxy XMPP accetta e invia i messaggi XMPP (Extensible Messaging and Presence Protocol) a e da partner federati XMPP configurati.</span><span class="sxs-lookup"><span data-stu-id="06bbb-123">**XMPP Proxy service**   The XMPP Proxy service accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>

<span data-ttu-id="06bbb-124">Gli utenti esterni autorizzati possono accedere ai server perimetrali per la connessione alla distribuzione interna di Lync Server 2013, ma i server perimetrali non forniscono un mezzo per qualsiasi altro accesso alla rete interna.</span><span class="sxs-lookup"><span data-stu-id="06bbb-124">Authorized external users can access the Edge Servers in order to connect to your internal Lync Server 2013 deployment, but the Edge Servers do not provide a means for any other access to the internal network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="06bbb-125">I server perimetrali vengono distribuiti per fornire connessioni per i client Lync abilitati e altri server perimetrali Microsoft (come negli scenari di federazione).</span><span class="sxs-lookup"><span data-stu-id="06bbb-125">Edge servers are deployed to provide connections for enabled Lync clients and other Microsoft Edge servers (as in federation scenarios).</span></span> <span data-ttu-id="06bbb-126">Non sono progettate per consentire connessioni da altri tipi di server o client di endpoint.</span><span class="sxs-lookup"><span data-stu-id="06bbb-126">They are not designed to allow connections from other end point client or server types.</span></span> <span data-ttu-id="06bbb-127">Il server gateway XMPP può essere distribuito per consentire le connessioni con i partner XMPP configurati.</span><span class="sxs-lookup"><span data-stu-id="06bbb-127">The XMPP Gateway server can be deployed to allow connections with configured XMPP partners.</span></span> <span data-ttu-id="06bbb-128">Il server perimetrale e il gateway XMPP sono in grado di supportare solo le connessioni a endpoint da questi tipi di client e di Federazione.</span><span class="sxs-lookup"><span data-stu-id="06bbb-128">The Edge server and XMPP Gateway can only support end point connections from these client and federation types.</span></span>



</div>

</div>

<div>

## <a name="reverse-proxy"></a><span data-ttu-id="06bbb-129">Proxy inverso</span><span class="sxs-lookup"><span data-stu-id="06bbb-129">Reverse Proxy</span></span>

<span data-ttu-id="06bbb-130">Questo proxy è necessario per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="06bbb-130">The reverse proxy is required for the following:</span></span>

  - <span data-ttu-id="06bbb-131">Consentire agli utenti di connettersi alle riunioni o alle conferenze telefoniche con accesso esterno utilizzando URL semplici</span><span class="sxs-lookup"><span data-stu-id="06bbb-131">To allow users to connect to meetings or dial-in conferences using simple URLs</span></span>

  - <span data-ttu-id="06bbb-132">Consentire agli utenti esterni di scaricare il contenuto delle riunioni</span><span class="sxs-lookup"><span data-stu-id="06bbb-132">To enable external users to download meeting content</span></span>

  - <span data-ttu-id="06bbb-133">Consentire agli utenti esterni di espandere i gruppi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="06bbb-133">To enable external users to expand distribution groups</span></span>

  - <span data-ttu-id="06bbb-134">Consentire all'utente di ottenere un certificato basato sugli utenti per l'autenticazione basata sui certificati client</span><span class="sxs-lookup"><span data-stu-id="06bbb-134">To allow the user to obtain a user-based certificate for client certificate based authentication</span></span>

  - <span data-ttu-id="06bbb-135">Consentire agli utenti remoti di scaricare file dal server della Rubrica o inviare query al servizio Address Book Web Query</span><span class="sxs-lookup"><span data-stu-id="06bbb-135">To enable remote users to download files from the Address Book Server or to submit queries to the Address Book Web Query service</span></span>

  - <span data-ttu-id="06bbb-136">Consentire agli utenti remoti di ottenere aggiornamenti per il software client e dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="06bbb-136">To enable remote users to obtain updates to client and device software</span></span>

  - <span data-ttu-id="06bbb-137">Consentire ai dispositivi mobili di individuare automaticamente i Front End Server che offrono servizi per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="06bbb-137">To enable mobile devices to automatically discover Front End Servers offering mobility services</span></span>

  - <span data-ttu-id="06bbb-138">Per abilitare le notifiche push ai dispositivi mobili da Microsoft 365, Office 365 o Apple Push Notification Services</span><span class="sxs-lookup"><span data-stu-id="06bbb-138">To enable push notifications to mobile devices from the Microsoft 365, Office 365, or Apple push notification services</span></span>

<span data-ttu-id="06bbb-139">Per ulteriori informazioni relative ai proxy inversi e ai requisiti che devono soddisfare i proxy inversi, vedere i dettagli nei [requisiti di configurazione per il proxy inverso in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="06bbb-139">For additional information related to reverse proxies and the requirements that reverse proxies must meet, see the details in [Configuration requirements for reverse proxy in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="06bbb-140">Gli utenti esterni non necessitano di una connessione VPN (Virtual Private Network) alla propria organizzazione per partecipare alle comunicazioni tramite Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="06bbb-140">External users do not need a virtual private network (VPN) connection to your organization in order to participate in communications using Lync Server 2013.</span></span> <span data-ttu-id="06bbb-141">Se la tecnologia VPN è stata implementata nell'organizzazione e gli utenti utilizzano la VPN per Lync, è possibile che il traffico multimediale, ad esempio le conferenze video, sia influenzato negativamente.</span><span class="sxs-lookup"><span data-stu-id="06bbb-141">If you have implemented VPN technology in your organization and your users use the VPN for Lync, media traffic (such as video conferencing) can be adversely affected.</span></span> <span data-ttu-id="06bbb-142">È consigliabile fornire un mezzo per il traffico multimediale per la connessione al servizio di AV Edge direttamente e ignorare la VPN.</span><span class="sxs-lookup"><span data-stu-id="06bbb-142">You should consider providing a means for media traffic to connect to the AV Edge service directly and bypass the VPN.</span></span> <span data-ttu-id="06bbb-143">Per informazioni dettagliate, vedere l'articolo del Blog di NextHop "Abilitazione di Lync media per ignorare un tunnel VPN" all'indirizzo <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A> .</span><span class="sxs-lookup"><span data-stu-id="06bbb-143">For details, see the NextHop Blog article, “Enabling Lync Media to Bypass a VPN Tunnel,” at <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A>.</span></span>



</div>

</div>

<div>

## <a name="firewall"></a><span data-ttu-id="06bbb-144">Firewall</span><span class="sxs-lookup"><span data-stu-id="06bbb-144">Firewall</span></span>

<span data-ttu-id="06bbb-145">È possibile distribuire la topologia perimetrale solo con un firewall esterno oppure con un firewall esterno e uno interno.</span><span class="sxs-lookup"><span data-stu-id="06bbb-145">You can deploy your edge topology with only an external firewall or both external and internal firewalls.</span></span> <span data-ttu-id="06bbb-146">Le architetture degli scenari includono due firewall.</span><span class="sxs-lookup"><span data-stu-id="06bbb-146">The scenario architectures include two firewalls.</span></span> <span data-ttu-id="06bbb-147">L'utilizzo di due firewall è il metodo consigliato poiché garantisce un routing rigoroso da un perimetro all'altro della rete e protegge la distribuzione interna con due livelli di firewall.</span><span class="sxs-lookup"><span data-stu-id="06bbb-147">Using two firewalls is the recommended approach because it ensures strict routing from one network edge to the other, and it protects your internal deployment behind two levels of firewall.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="06bbb-148">Director</span><span class="sxs-lookup"><span data-stu-id="06bbb-148">Director</span></span>

<span data-ttu-id="06bbb-149">Un Director è un ruolo del server facoltativo separato in Lync Server 2013 che non ospita account utente o che fornisce servizi di conferenza o presenza.</span><span class="sxs-lookup"><span data-stu-id="06bbb-149">A Director is a separate, optional server role in Lync Server 2013 that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="06bbb-150">Funge da server hop successivo interno a cui un server perimetrale instrada il traffico SIP in ingresso destinato ai server interni.</span><span class="sxs-lookup"><span data-stu-id="06bbb-150">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="06bbb-151">Il Director preautentica le richieste in ingresso e le reindirizza al pool o al server Home dell'utente.</span><span class="sxs-lookup"><span data-stu-id="06bbb-151">The Director preauthenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="06bbb-152">Eseguendo la preautenticazione presso il server Director, è possibile eliminare le richieste dagli account utente sconosciute alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="06bbb-152">By preauthenticating at the Director, you can drop requests from user accounts that are unknown to the deployment.</span></span>

<span data-ttu-id="06bbb-153">Un amministratore consente di isolare i server Standard Edition e front end server in pool Enterprise Edition front end da traffico dannoso, ad esempio attacchi DoS (Denial of Service).</span><span class="sxs-lookup"><span data-stu-id="06bbb-153">A Director helps insulate Standard Edition servers and Front End Servers in Enterprise Edition Front End pools from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="06bbb-154">Se la rete viene inondata di traffico esterno non valido in un attacco di questo tipo, il traffico termina nel server Director.</span><span class="sxs-lookup"><span data-stu-id="06bbb-154">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span> <span data-ttu-id="06bbb-155">Per informazioni dettagliate sull'utilizzo dei direttori, vedere [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="06bbb-155">For details about the use of Directors, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="06bbb-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06bbb-156">See Also</span></span>


[<span data-ttu-id="06bbb-157">Requisiti per il bilanciamento del carico hardware per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06bbb-157">Hardware load balancer requirements for Lync Server 2013</span></span>](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

