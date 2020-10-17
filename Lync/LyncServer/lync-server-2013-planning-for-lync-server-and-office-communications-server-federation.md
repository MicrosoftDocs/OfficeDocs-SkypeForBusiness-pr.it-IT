---
title: Pianificazione della Federazione di Lync Server e Office Communications Server
description: Pianificazione della Federazione di Lync Server e Office Communications Server.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d7385b8fde27446fb0648802544a8840a0f6276
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552372"
---
# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a><span data-ttu-id="5a520-103">Planning for Lync Server 2013 e Office Communications Server Federation</span><span class="sxs-lookup"><span data-stu-id="5a520-103">Planning for Lync Server 2013 and Office Communications Server federation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a520-104">_**Ultimo argomento modificato:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="5a520-104">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="5a520-105">La Federazione tra Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server supporta le comunicazioni peer-to-peer e multi-party.</span><span class="sxs-lookup"><span data-stu-id="5a520-105">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="5a520-106">È possibile effettuare l'escalation delle conversazioni peer-to-peer a conversazioni tra più parti, consentendo l'esecuzione di riunioni ad hoc.</span><span class="sxs-lookup"><span data-stu-id="5a520-106">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="5a520-107">Le riunioni, che possono essere conferenze Web o conferenze audio/video, possono essere pianificate in modo da includere contatti all'interno dell'organizzazione e contatti partner con cui si attua la federazione.</span><span class="sxs-lookup"><span data-stu-id="5a520-107">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="5a520-108">La Federazione è stata introdotta per la prima volta in Microsoft Office Live Communications Server 2005 e ha supportato un tipo di federazione, Direct Federation.</span><span class="sxs-lookup"><span data-stu-id="5a520-108">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="5a520-109">Direct Federation richiede di conoscere il dominio SIP (Session Initiation Protocol) del partner federativo e il nome di dominio completo (FQDN) del server perimetrale del partner.</span><span class="sxs-lookup"><span data-stu-id="5a520-109">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="5a520-110">In Live Communications Server 2005 con SP1 sono stati introdotti altri tipi di federazione, tutti i quali sono necessari record SRV DNS (Domain Name System) che devono essere pubblicati dal partner federato per individuare il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="5a520-110">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="5a520-111">La terminologia relativa a tale versione è stata la seguente:</span><span class="sxs-lookup"><span data-stu-id="5a520-111">The terminology for that release was:</span></span>

  - <span data-ttu-id="5a520-112">*Aprire Federazione avanzata*: accettare qualsiasi nome di dominio SIP e utilizzare DNS SRV per individuare il server perimetrale partner</span><span class="sxs-lookup"><span data-stu-id="5a520-112">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="5a520-113">*Federazione avanzata*: configurare il nome di dominio SIP del partner come partner federativo per l'organizzazione e utilizzare DNS SRV per trovare il server perimetrale del partner</span><span class="sxs-lookup"><span data-stu-id="5a520-113">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="5a520-114">*Federazione diretta*: configurare il nome di dominio SIP del partner e l'FQDN nel server perimetrale del partner</span><span class="sxs-lookup"><span data-stu-id="5a520-114">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="5a520-115">*Elenco Consenti server*: accettare qualsiasi dominio, utilizzare DNS SRV per individuare il server perimetrale di un provider di hosting o di un provider di connettività per la messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="5a520-115">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="5a520-116">Microsoft Office Communications Server 2007 ha introdotto la denominazione aggiornata per i tipi di federazione per definire meglio ciò che ogni tipo di Federazione ha effettivamente ottenuto:</span><span class="sxs-lookup"><span data-stu-id="5a520-116">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="5a520-117">La federazione avanzata aperta è stata denominata *dominio individuato del partner*.</span><span class="sxs-lookup"><span data-stu-id="5a520-117">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="5a520-118">La federazione avanzata è stata denominata *dominio partner consentito*.</span><span class="sxs-lookup"><span data-stu-id="5a520-118">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="5a520-119">La federazione diretta è stata denominata *server partner consentito*.</span><span class="sxs-lookup"><span data-stu-id="5a520-119">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="5a520-120">L'elenco dei server consentiti è stato denominato *provider di hosting* e *provider di servizi di messaggistica istantanea pubblica*.</span><span class="sxs-lookup"><span data-stu-id="5a520-120">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="5a520-121">Microsoft Lync Server 2010 ha introdotto una definizione più restrittiva del provider di hosting in conformità con Microsoft Lync Online 2010 e Microsoft Office 365 e ha anche reso soggetto allo stesso elenco consentito definito dal tipo di Federazione del dominio del partner consentito.</span><span class="sxs-lookup"><span data-stu-id="5a520-121">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="5a520-122">L'abilitazione della Federazione tra Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server utilizza i server perimetrali e i proxy inversi per applicare le regole e i domini partner consentiti definiti.</span><span class="sxs-lookup"><span data-stu-id="5a520-122">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="5a520-123">Da un punto di vista della pianificazione, la Federazione con altri Lync Server, Office Communications Server richiede quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5a520-123">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="5a520-124">Abilitare la federazione in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="5a520-124">Enable federation in Topology Builder.</span></span> <span data-ttu-id="5a520-125">Per informazioni dettagliate, vedere la sezione relativa alla distribuzione di [federazione SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="5a520-125">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="5a520-126">Determinare i propri requisiti per l'individuazione del dominio federato:</span><span class="sxs-lookup"><span data-stu-id="5a520-126">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="5a520-127">Per la configurazione manuale della Federazione, è necessario disporre del nome di dominio completo (FQDN) del server perimetrale e del nome di dominio del partner oppure del nome di dominio online, immesso nel pannello di controllo di Lync Server, nella **Federazione e nell'accesso esterno**, ovvero nei **domini federati SIP**.</span><span class="sxs-lookup"><span data-stu-id="5a520-127">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="5a520-128">Creare nuovi criteri facendo clic su **Nuovo** oppure modificare criteri esistenti facendo clic su **Modifica** in modo da consentire o bloccare i domini in base all'FQDN.</span><span class="sxs-lookup"><span data-stu-id="5a520-128">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="5a520-129">La configurazione manuale del server perimetrale di un partner federativo è soggetta a un errore nel caso in cui il partner modifichi l'indirizzo IP del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="5a520-129">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="5a520-130">Per i <STRONG>nuovi domini federati SIP</STRONG>, è necessario fornire il <STRONG>nome di dominio (o FQDN)</STRONG> per Microsoft Lync Online e microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="5a520-130">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online and Microsoft 365 or Office 365.</span></span> <span data-ttu-id="5a520-131">Per Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server è inoltre necessario fornire un <STRONG>servizio Access Edge (FQDN)</STRONG></span><span class="sxs-lookup"><span data-stu-id="5a520-131">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="5a520-132">Per la Federazione partner individuata, in cui i partner possono individuare il server perimetrale, è necessario creare un record SRV nel DNS esterno- \_ sipfederationtls. \_ tcp.contoso.com – che punta alla porta 5061 e al record host (A) del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="5a520-132">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="5a520-133">Se si supportano client Microsoft Lync Mobile su Windows Phone o Apple iPhone, iPad o altri dispositivi Apple e si utilizza il servizio di notifica push o di notifica push, è necessario pianificare _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="5a520-133">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="5a520-134">&lt;&gt;Record SRV di dominio SIP per ogni dominio SIP di cui si dispone di client mobili di Lync.</span><span class="sxs-lookup"><span data-stu-id="5a520-134">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="5a520-135">Android e Nokia Symbian Lync mobile non utilizzano la notifica push e non sono soggetti a questo requisito.</span><span class="sxs-lookup"><span data-stu-id="5a520-135">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="5a520-136">Configurare criteri di accesso utenti esterni per il supporto dei domini federati.</span><span class="sxs-lookup"><span data-stu-id="5a520-136">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="5a520-137">Aprire le porte del firewall per il protocollo SIP (Session Initiation Protocol), le conferenze Web e le conferenze audio/video per supportare la federazione o i contatti abilitati.</span><span class="sxs-lookup"><span data-stu-id="5a520-137">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="5a520-138">Per informazioni dettagliate, vedere: [determinare i requisiti di porte e firewall a/V esterni per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="5a520-138">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="5a520-139">Le informazioni seguenti consentono di definire il certificato, il protocollo e i requisiti DNS per la Federazione con Microsoft Lync Server 2013 e Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5a520-139">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="5a520-140">La pianificazione per i certificati, i requisiti del firewall e del protocollo di trasporto e i requisiti DNS è in genere un processo diretto se sono stati pianificati o distribuiti i server perimetrali di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5a520-140">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="5a520-141">Poiché la Federazione è una funzionalità aggiuntiva che utilizza il server perimetrale esistente, i requisiti di pianificazione vengono in genere soddisfatti dalla pianificazione e dalla distribuzione del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="5a520-141">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="5a520-142">È consigliabile utilizzare le tabelle seguenti per verificare che i requisiti vengano soddisfatti e apportare eventuali modifiche a porte/protocolli e DNS in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="5a520-142">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="5a520-143">Se si dispone di un pool di server perimetrali e si esegue la Federazione con i partner di Lync Server 2013 o Lync Server 2010, è possibile utilizzare il bilanciamento del carico DNS o i dispositivi di bilanciamento del carico hardware sui lati interni ed esterni dei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="5a520-143">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="5a520-144">Se si sta effettuando la Federazione con Office Communications Server 2007 o Office Communications Server 2007 R2, il bilanciamento del carico hardware fornirà supporto per il failover nel caso di un server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="5a520-144">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="5a520-145">Office Communications Server 2007 e Office Communications Server 2007 R2 non sono compatibili con il bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="5a520-145">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="5a520-146">I server perimetrali partner stabiliranno la comunicazione con il primo server perimetrale del pool che risponde.</span><span class="sxs-lookup"><span data-stu-id="5a520-146">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="5a520-147">Se il server perimetrale ha esito negativo, la comunicazione non esegue automaticamente il failover.</span><span class="sxs-lookup"><span data-stu-id="5a520-147">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="5a520-148">I requisiti dei certificati vengono in genere soddisfatti tramite la pianificazione di certificati per il server perimetrale o il piano server perimetrale scelto.</span><span class="sxs-lookup"><span data-stu-id="5a520-148">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5a520-149">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="5a520-149">In This Section</span></span>

  - [<span data-ttu-id="5a520-150">Riepilogo del certificato-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a520-150">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="5a520-151">Riepilogo delle porte-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a520-151">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="5a520-152">Riepilogo DNS-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a520-152">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5a520-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a520-153">See Also</span></span>


[<span data-ttu-id="5a520-154">Configurare criteri per controllare l'accesso degli utenti federati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a520-154">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="5a520-155">Scenari per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a520-155">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="5a520-156">Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a520-156">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="5a520-157">Determinare i requisiti DNS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a520-157">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="5a520-158">Gestire la configurazione di Access Edge per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a520-158">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="5a520-159">Gestire i domini federati SIP per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a520-159">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="5a520-160">Gestire i provider federati SIP per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a520-160">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

