---
title: Pianificazione per Lync Server e Office Communications Server Federation
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
ms.openlocfilehash: 015f824ff2b8510559a7bd4910be76321d44d242
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a><span data-ttu-id="2a2bc-102">Pianificazione per Lync Server 2013 e Office Communications Server Federation</span><span class="sxs-lookup"><span data-stu-id="2a2bc-102">Planning for Lync Server 2013 and Office Communications Server federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a2bc-103">_**Argomento Ultima modifica:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="2a2bc-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="2a2bc-104">La Federazione tra Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server supporta le comunicazioni peer-to-peer e multiparty.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-104">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="2a2bc-105">Le conversazioni peer-to-peer possono essere Escalate in conversazioni multiparte, consentendo riunioni ad hoc.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-105">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="2a2bc-106">Riunioni-conferenza Web o conferenze audio/visive-può essere programmato per includere i contatti all'interno dell'organizzazione e i contatti nei partner con cui si federa.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-106">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="2a2bc-107">La Federazione è stata pubblicata per la prima volta in Microsoft Office Live Communications Server 2005 e ha supportato un tipo di federazione, Direct Federation.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-107">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="2a2bc-108">Direct Federation richiede di conoscere il dominio SIP (Session Initiation Protocol) del partner federativo e il nome di dominio completo (FQDN) del server Edge del partner.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-108">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="2a2bc-109">In Live Communications Server 2005 con SP1 sono stati introdotti altri tipi di federazione, tutti i quali sono necessari record SRV DNS (Domain Name System) che devono essere pubblicati dal partner federativo per individuare il proprio Edge Server.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-109">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="2a2bc-110">La terminologia relativa a tale versione è stata:</span><span class="sxs-lookup"><span data-stu-id="2a2bc-110">The terminology for that release was:</span></span>

  - <span data-ttu-id="2a2bc-111">*Aprire la federazione avanzata*: accettare qualsiasi nome di dominio SIP e usare DNS SRV per individuare il server Edge partner</span><span class="sxs-lookup"><span data-stu-id="2a2bc-111">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="2a2bc-112">*Federazione avanzata*: configurare il nome di dominio SIP del partner come partner federativo per l'organizzazione e usare DNS SRV per trovare il server Edge partner</span><span class="sxs-lookup"><span data-stu-id="2a2bc-112">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="2a2bc-113">*Federazione diretta*: configurare il nome di dominio SIP del partner e l'FQDN nel server perimetrale del partner</span><span class="sxs-lookup"><span data-stu-id="2a2bc-113">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="2a2bc-114">*Elenco Consenti server*: accettare qualsiasi dominio, usare DNS SRV per trovare il server perimetrale di un provider di hosting o di un provider di connettività messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="2a2bc-114">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="2a2bc-115">Microsoft Office Communications Server 2007 ha introdotto la denominazione aggiornata per i tipi di federazione per definire in modo più efficace il risultato di ogni tipo di Federazione:</span><span class="sxs-lookup"><span data-stu-id="2a2bc-115">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="2a2bc-116">Aprire la federazione avanzata divenne nota come *dominio del partner individuato*</span><span class="sxs-lookup"><span data-stu-id="2a2bc-116">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="2a2bc-117">La federazione avanzata divenne nota come *dominio del partner consentito*</span><span class="sxs-lookup"><span data-stu-id="2a2bc-117">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="2a2bc-118">La Federazione diretta divenne nota come *server partner consentiti*</span><span class="sxs-lookup"><span data-stu-id="2a2bc-118">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="2a2bc-119">L'elenco dei server consentiti divenne noto come *provider di hosting* e *provider di messaggistica istantanea pubblica*</span><span class="sxs-lookup"><span data-stu-id="2a2bc-119">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="2a2bc-120">Microsoft Lync Server 2010 ha introdotto una definizione più ristretta del provider di hosting in conformità con Microsoft Lync Online 2010 e Microsoft Office 365 e lo ha anche reso soggetto allo stesso elenco consentiti definito dal tipo di Federazione del dominio partner consentito.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-120">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="2a2bc-121">L'abilitazione della Federazione tra Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server usa gli Edge Server e i proxy inversi per applicare le regole e i domini partner consentiti che si definiscono.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-121">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="2a2bc-122">Da un punto di vista della pianificazione, la Federazione con altri server Lync, Office Communications Server richiede quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2a2bc-122">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="2a2bc-123">Abilitare la Federazione in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-123">Enable federation in Topology Builder.</span></span> <span data-ttu-id="2a2bc-124">Per informazioni dettagliate, vedere l'argomento sulla distribuzione [configurazione della Federazione SIP, della Federazione XMPP e della messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="2a2bc-124">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="2a2bc-125">Determinare i requisiti per l'individuazione di domini federati:</span><span class="sxs-lookup"><span data-stu-id="2a2bc-125">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="2a2bc-126">Per la configurazione manuale della Federazione, è necessario avere il nome di dominio completo (FQDN) del server perimetrale e del nome di dominio del partner oppure il nome di dominio online, che viene immesso nel pannello di controllo di Lync Server, nella **Federazione e nell'accesso esterno**, i **domini federati SIP**.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-126">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="2a2bc-127">Creare un **nuovo** criterio o **modificare** un criterio esistente per consentire o bloccare i domini in base al nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-127">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="2a2bc-128">La configurazione manuale di un Edge Server del partner federativo è soggetta a un errore se il partner cambia l'indirizzo IP del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-128">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="2a2bc-129">Per i <STRONG>nuovi domini federati SIP</STRONG>, è necessario specificare il <STRONG>nome di dominio (o FQDN)</STRONG> per Microsoft Lync Online, Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-129">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="2a2bc-130">Per Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server è necessario specificare anche un <STRONG>servizio di Access Edge (FQDN)</STRONG></span><span class="sxs-lookup"><span data-stu-id="2a2bc-130">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="2a2bc-131">Per la Federazione partner scoperta, in cui i partner possono individuare l'Edge Server, è possibile creare un record SRV nel \_DNS esterno-sipfederationtls. \_TCP.contoso.com-che punta alla porta 5061 e al record host (a) del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="2a2bc-131">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="2a2bc-132">Se si supportano i client Microsoft Lync Mobile su Windows Phone o Apple iPhone, iPad o altri dispositivi Apple e si usa il servizio di notifica push o il servizio di notifica push, è necessario pianificare _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-132">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="2a2bc-133">&lt;SIP Domain&gt; record SRV per ogni dominio SIP in cui sono presenti client mobili Lync.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-133">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="2a2bc-134">Android e Nokia Symbian Lync mobile non usano la notifica push e non sono soggetti a questo requisito.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-134">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="2a2bc-135">Configurare i criteri di accesso degli utenti esterni per supportare i domini federati</span><span class="sxs-lookup"><span data-stu-id="2a2bc-135">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="2a2bc-136">Aprire le porte del firewall per SIP (Session Initiation Protocol), Web Conferencing e Audio/Visual per supportare la Federazione o i contatti che si stanno abilitando.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-136">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="2a2bc-137">Per informazioni dettagliate, vedere: [determinare i requisiti per il firewall e la porta esterni a/V per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="2a2bc-137">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="2a2bc-138">Le informazioni seguenti ti aiuteranno a definire i requisiti di certificato, porta/protocollo e DNS per la Federazione con Microsoft Lync Server 2013 e Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-138">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="2a2bc-139">La pianificazione per i certificati, i requisiti per il firewall e la porta/protocollo e i requisiti DNS è in genere un processo semplice se si è pianificato o distribuito i server Edge di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-139">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="2a2bc-140">Dato che Federation è una funzionalità aggiuntiva che usa il server perimetrale esistente, i requisiti di pianificazione vengono in genere soddisfatti dalla pianificazione e distribuzione di Edge Server.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-140">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="2a2bc-141">È consigliabile usare le tabelle seguenti per determinare che i requisiti sono soddisfatti e apportare le modifiche in porta/protocollo e DNS di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-141">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="2a2bc-142">Se si dispone di un pool di Edge Server e si esegue la Federazione con i partner di Lync Server 2013 o Lync Server 2010, è possibile usare i dispositivi di bilanciamento del carico DNS o di bilanciamento del carico hardware sui lati interni ed esterni degli Edge Server.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-142">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="2a2bc-143">Se si esegue la Federazione con Office Communications Server 2007 o Office Communications Server 2007 R2, il bilanciamento del carico hardware fornirà il supporto per il failover in caso di un server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-143">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="2a2bc-144">Office Communications Server 2007 e Office Communications Server 2007 R2 non supportano il bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-144">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="2a2bc-145">I server Edge partner stabiliscono le comunicazioni con il primo Edge Server nel pool che risponde.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-145">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="2a2bc-146">Se il server perimetrale non riesce, la comunicazione non esegue automaticamente il failover.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-146">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="2a2bc-147">I requisiti di certificato vengono in genere soddisfatti tramite la pianificazione di certificati per il piano server Edge o pooled Edge scelto.</span><span class="sxs-lookup"><span data-stu-id="2a2bc-147">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2a2bc-148">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="2a2bc-148">In This Section</span></span>

  - [<span data-ttu-id="2a2bc-149">Riepilogo del certificato-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a2bc-149">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="2a2bc-150">Riepilogo della porta-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a2bc-150">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="2a2bc-151">Riepilogo DNS-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a2bc-151">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2a2bc-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a2bc-152">See Also</span></span>


[<span data-ttu-id="2a2bc-153">Configurare criteri per controllare l'accesso utente federato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a2bc-153">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="2a2bc-154">Scenari per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a2bc-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="2a2bc-155">Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a2bc-155">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="2a2bc-156">Determinare i requisiti di DNS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a2bc-156">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="2a2bc-157">Gestire la configurazione Access Edge per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a2bc-157">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="2a2bc-158">Gestire i domini federati SIP per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a2bc-158">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="2a2bc-159">Gestire i provider federati SIP per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a2bc-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

