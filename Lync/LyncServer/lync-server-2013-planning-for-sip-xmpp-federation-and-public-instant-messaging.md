---
title: Pianificazione per SIP, Federazione XMPP e messaggistica istantanea pubblica
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 994a1395363c28976c8bbfe325edae99e97cdc48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="3d13d-102">Pianificazione per SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d13d-102">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d13d-103">_**Argomento Ultima modifica:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="3d13d-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="3d13d-104">I server perimetrali possono essere configurati per consentire agli utenti interni e esterni di accedere ai contatti presso organizzazioni o servizi partner.</span><span class="sxs-lookup"><span data-stu-id="3d13d-104">Edge Servers can be configured to allow your internal and external users access to contacts at partner organizations or services.</span></span> <span data-ttu-id="3d13d-105">Le federazioni, dato che questi accordi con i partner sono note, possono eseguire una o tutte le operazioni seguenti ai contatti dell'organizzazione nella Federazione partner o nei contatti della Federazione partner:</span><span class="sxs-lookup"><span data-stu-id="3d13d-105">Federations, as these partner agreements are known, can provide any or all of the following to the contacts in your organization on the partner federation or contacts in the partner federation to yours:</span></span>

  - <span data-ttu-id="3d13d-106">Messaggistica istantanea e presenza</span><span class="sxs-lookup"><span data-stu-id="3d13d-106">Instant messaging and presence</span></span>

  - <span data-ttu-id="3d13d-107">Collaborazione e conferenze, ad esempio-Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="3d13d-107">Collaboration and conferencing, for example – Web conferencing</span></span>

  - <span data-ttu-id="3d13d-108">Servizi di conferenza audio, videoconferenza o entrambi</span><span class="sxs-lookup"><span data-stu-id="3d13d-108">Audio conferencing, video conferencing, or both</span></span>

<span data-ttu-id="3d13d-109">In alcuni casi, la comunicazione, ad esempio messaggistica istantanea e presenza tra un Microsoft Lync Server 2013 e un contatto XMPP (Extensible Messaging and Presence Protocol), è solo peer-to-peer: supporta solo l'utente e il contatto presso la federati partner.</span><span class="sxs-lookup"><span data-stu-id="3d13d-109">In some cases the communication, for example instant messaging (IM) and presence between a Microsoft Lync Server 2013 and an extensible messaging and presence protocol (XMPP) contact, is peer-to-peer only - supporting only you and the contact at the federated partner.</span></span> <span data-ttu-id="3d13d-110">In altri casi, ad esempio un server Lync, Lync Server 2010 alla federazione Lync Server 2013, è possibile invitare più partecipanti a partecipare alla conversazione.</span><span class="sxs-lookup"><span data-stu-id="3d13d-110">In other cases, such as a Lync Server, Lync Server 2010 to Lync Server 2013 federation, multiple participants can be invited to join into the conversation.</span></span>

<div>

## <a name="lync-server-and-office-communications-server-federation"></a><span data-ttu-id="3d13d-111">Lync Server e Office Communications Server Federation</span><span class="sxs-lookup"><span data-stu-id="3d13d-111">Lync Server and Office Communications Server Federation</span></span>

<span data-ttu-id="3d13d-112">La Federazione tra Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server supporta le comunicazioni peer-to-peer e multiparty.</span><span class="sxs-lookup"><span data-stu-id="3d13d-112">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="3d13d-113">Le conversazioni peer-to-peer possono essere Escalate in conversazioni multiparte, consentendo riunioni ad hoc.</span><span class="sxs-lookup"><span data-stu-id="3d13d-113">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="3d13d-114">Riunioni-conferenza Web o conferenze audio/visive-può essere programmato per includere i contatti all'interno dell'organizzazione e i contatti nei partner con cui si federa.</span><span class="sxs-lookup"><span data-stu-id="3d13d-114">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="3d13d-115">La Federazione è stata pubblicata per la prima volta in Microsoft Office Live Communications Server 2005 e ha supportato un tipo di federazione, Direct Federation.</span><span class="sxs-lookup"><span data-stu-id="3d13d-115">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="3d13d-116">Direct Federation richiede di conoscere il dominio SIP (Session Initiation Protocol) del partner federativo e il nome di dominio completo (FQDN) del server Edge del partner.</span><span class="sxs-lookup"><span data-stu-id="3d13d-116">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="3d13d-117">In Live Communications Server 2005 con SP1 sono stati introdotti altri tipi di federazione, tutti i quali sono necessari record SRV DNS (Domain Name System) che devono essere pubblicati dal partner federativo per individuare il proprio Edge Server.</span><span class="sxs-lookup"><span data-stu-id="3d13d-117">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="3d13d-118">La terminologia relativa a tale versione è stata:</span><span class="sxs-lookup"><span data-stu-id="3d13d-118">The terminology for that release was:</span></span>

  - <span data-ttu-id="3d13d-119">*Aprire la federazione avanzata*: accettare qualsiasi nome di dominio SIP e usare DNS SRV per individuare il server Edge partner</span><span class="sxs-lookup"><span data-stu-id="3d13d-119">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="3d13d-120">*Federazione avanzata*: configurare il nome di dominio SIP del partner come partner federativo per l'organizzazione e usare DNS SRV per trovare il server Edge partner</span><span class="sxs-lookup"><span data-stu-id="3d13d-120">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="3d13d-121">*Federazione diretta*: configurare il nome di dominio SIP del partner e l'FQDN nel server perimetrale del partner</span><span class="sxs-lookup"><span data-stu-id="3d13d-121">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="3d13d-122">*Elenco Consenti server*: accettare qualsiasi dominio, usare DNS SRV per trovare il server perimetrale di un provider di hosting o di un provider di connettività messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="3d13d-122">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="3d13d-123">Microsoft Office Communications Server 2007 ha introdotto la denominazione aggiornata per i tipi di federazione per definire in modo più efficace il risultato di ogni tipo di Federazione:</span><span class="sxs-lookup"><span data-stu-id="3d13d-123">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="3d13d-124">Aprire la federazione avanzata divenne nota come *dominio del partner individuato*</span><span class="sxs-lookup"><span data-stu-id="3d13d-124">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="3d13d-125">La federazione avanzata divenne nota come *dominio del partner consentito*</span><span class="sxs-lookup"><span data-stu-id="3d13d-125">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="3d13d-126">La Federazione diretta divenne nota come *server partner consentiti*</span><span class="sxs-lookup"><span data-stu-id="3d13d-126">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="3d13d-127">L'elenco dei server consentiti divenne noto come *provider di hosting* e *provider di messaggistica istantanea pubblica*</span><span class="sxs-lookup"><span data-stu-id="3d13d-127">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="3d13d-128">Microsoft Lync Server 2010 ha introdotto una definizione più ristretta del provider di hosting in conformità con Microsoft Lync Online 2010 e Microsoft Office 365 e lo ha anche reso soggetto allo stesso elenco consentiti definito dal tipo di Federazione del dominio partner consentito.</span><span class="sxs-lookup"><span data-stu-id="3d13d-128">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="3d13d-129">L'abilitazione della Federazione tra Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server usa gli Edge Server e i proxy inversi per applicare le regole e i domini partner consentiti che si definiscono.</span><span class="sxs-lookup"><span data-stu-id="3d13d-129">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="3d13d-130">Da un punto di vista della pianificazione, la Federazione con altri server Lync, Office Communications Server richiede quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3d13d-130">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="3d13d-131">Abilitare la Federazione in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="3d13d-131">Enable federation in Topology Builder.</span></span> <span data-ttu-id="3d13d-132">Per informazioni dettagliate, vedere l'argomento sulla distribuzione [configurazione della Federazione SIP, della Federazione XMPP e della messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="3d13d-132">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="3d13d-133">Determinare i requisiti per l'individuazione di domini federati:</span><span class="sxs-lookup"><span data-stu-id="3d13d-133">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="3d13d-134">Per la configurazione manuale della Federazione, è necessario avere il nome di dominio completo (FQDN) del server perimetrale e del nome di dominio del partner oppure il nome di dominio online, che viene immesso nel pannello di controllo di Lync Server, nella **Federazione e nell'accesso esterno**, i **domini federati SIP**.</span><span class="sxs-lookup"><span data-stu-id="3d13d-134">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="3d13d-135">Creare un **nuovo** criterio o **modificare** un criterio esistente per consentire o bloccare i domini in base al nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="3d13d-135">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="3d13d-136">La configurazione manuale di un Edge Server del partner federativo è soggetta a un errore se il partner cambia l'indirizzo IP del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="3d13d-136">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="3d13d-137">Per i <STRONG>nuovi domini federati SIP</STRONG>, è necessario specificare il <STRONG>nome di dominio (o FQDN)</STRONG> per Microsoft Lync Online, Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="3d13d-137">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="3d13d-138">Per Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server è necessario specificare anche un <STRONG>servizio di Access Edge (FQDN)</STRONG></span><span class="sxs-lookup"><span data-stu-id="3d13d-138">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="3d13d-139">Per la Federazione partner scoperta, in cui i partner possono individuare l'Edge Server, è possibile creare un record SRV nel \_DNS esterno-sipfederationtls. \_TCP.contoso.com-che punta alla porta 5061 e al record host (a) del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="3d13d-139">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="3d13d-140">Se si supportano i client Microsoft Lync Mobile su Windows Phone o Apple iPhone, iPad o altri dispositivi Apple e si usa il servizio di notifica push o il servizio di notifica push, è necessario pianificare _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="3d13d-140">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="3d13d-141">&lt;SIP Domain&gt; record SRV per ogni dominio SIP in cui sono presenti client mobili Lync.</span><span class="sxs-lookup"><span data-stu-id="3d13d-141">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="3d13d-142">Android e Nokia Symbian Lync mobile non usano la notifica push e non sono soggetti a questo requisito.</span><span class="sxs-lookup"><span data-stu-id="3d13d-142">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="3d13d-143">Configurare i criteri di accesso degli utenti esterni per supportare i domini federati</span><span class="sxs-lookup"><span data-stu-id="3d13d-143">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="3d13d-144">Aprire le porte del firewall per SIP (Session Initiation Protocol), Web Conferencing e Audio/Visual per supportare la Federazione o i contatti che si stanno abilitando.</span><span class="sxs-lookup"><span data-stu-id="3d13d-144">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="3d13d-145">Per informazioni dettagliate, vedere: [determinare i requisiti per il firewall e la porta esterni a/V per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="3d13d-145">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="3d13d-146">Le informazioni seguenti ti aiuteranno a definire i requisiti di certificato, porta/protocollo e DNS per la Federazione con Microsoft Lync Server 2013 e Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3d13d-146">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="3d13d-147">La pianificazione per i certificati, i requisiti per il firewall e la porta/protocollo e i requisiti DNS è in genere un processo semplice se si è pianificato o distribuito i server Edge di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d13d-147">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="3d13d-148">Dato che Federation è una funzionalità aggiuntiva che usa il server perimetrale esistente, i requisiti di pianificazione vengono in genere soddisfatti dalla pianificazione e distribuzione di Edge Server.</span><span class="sxs-lookup"><span data-stu-id="3d13d-148">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="3d13d-149">È consigliabile usare le tabelle seguenti per determinare che i requisiti sono soddisfatti e apportare le modifiche in porta/protocollo e DNS di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="3d13d-149">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="3d13d-150">Se si dispone di un pool di Edge Server e si esegue la Federazione con i partner di Lync Server 2013 o Lync Server 2010, è possibile usare i dispositivi di bilanciamento del carico DNS o di bilanciamento del carico hardware sui lati interni ed esterni degli Edge Server.</span><span class="sxs-lookup"><span data-stu-id="3d13d-150">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="3d13d-151">Se si esegue la Federazione con Office Communications Server 2007 o Office Communications Server 2007 R2, il bilanciamento del carico hardware fornirà il supporto per il failover in caso di un server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="3d13d-151">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="3d13d-152">Office Communications Server 2007 e Office Communications Server 2007 R2 non supportano il bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="3d13d-152">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="3d13d-153">I server Edge partner stabiliscono le comunicazioni con il primo Edge Server nel pool che risponde.</span><span class="sxs-lookup"><span data-stu-id="3d13d-153">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="3d13d-154">Se il server perimetrale non riesce, la comunicazione non esegue automaticamente il failover.</span><span class="sxs-lookup"><span data-stu-id="3d13d-154">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="3d13d-155">I requisiti di certificato vengono in genere soddisfatti tramite la pianificazione di certificati per il piano server Edge o pooled Edge scelto.</span><span class="sxs-lookup"><span data-stu-id="3d13d-155">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a><span data-ttu-id="3d13d-156">Connettività di messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="3d13d-156">Public Instant Messaging Connectivity</span></span>

<span data-ttu-id="3d13d-157">La connettività di messaggistica istantanea pubblica è una classe di federazione ed è configurata per consentire agli utenti interni ed esterni di Lync Server 2013 di aggiungere contatti da una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d13d-157">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="3d13d-158">Contatti di Messenger</span><span class="sxs-lookup"><span data-stu-id="3d13d-158">Messenger contacts</span></span>

  - <span data-ttu-id="3d13d-159">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="3d13d-159">Yahoo\!</span></span> <span data-ttu-id="3d13d-160">contatti</span><span class="sxs-lookup"><span data-stu-id="3d13d-160">contacts</span></span>

  - <span data-ttu-id="3d13d-161">Contatti di America Online (AOL)</span><span class="sxs-lookup"><span data-stu-id="3d13d-161">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="3d13d-162">A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User (PIC USL) non è più disponibile per l'acquisto di contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="3d13d-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="3d13d-163">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="3d13d-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="3d13d-164">Messenger fino alla data di chiusura del servizio (la data esatta deve ancora essere decisa, ma non prima del 2013 giugno).</span><span class="sxs-lookup"><span data-stu-id="3d13d-164">Messenger until the service shutdown date (exact date is still to be decided, but no sooner than June 2013).</span></span></P>
> <LI>
> <P><span data-ttu-id="3d13d-165">Il PIC USL è una licenza per abbonamento per utente, per mese necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="3d13d-165">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="3d13d-166">Messenger.</span><span class="sxs-lookup"><span data-stu-id="3d13d-166">Messenger.</span></span> <span data-ttu-id="3d13d-167">La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto da Yahoo!, l'accordo sottostante per il quale non verrà rinnovato.</span><span class="sxs-lookup"><span data-stu-id="3d13d-167">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="3d13d-168">Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="3d13d-168">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="3d13d-169">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="3d13d-169">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="3d13d-170">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone tramite messaggistica istantanea e voce.</span><span class="sxs-lookup"><span data-stu-id="3d13d-170">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="3d13d-171">Questa classe di federazione richiede le seguenti considerazioni sulla pianificazione:</span><span class="sxs-lookup"><span data-stu-id="3d13d-171">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="3d13d-172">Gli utenti di Windows Live Messenger possono avere comunicazioni audio/visive peer-to-peer con gli utenti di Lync Server 2013, oltre alla messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="3d13d-172">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="3d13d-173">Gli Edge Server devono soddisfare requisiti specifici per la porta e il protocollo.</span><span class="sxs-lookup"><span data-stu-id="3d13d-173">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="3d13d-174">Per informazioni dettagliate, vedere [determinare i requisiti del firewall e della porta a/V esterni per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d13d-174">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="3d13d-175">La messaggistica istantanea di Yahoo non ha requisiti univoci, ad eccezione di quelli usati in genere nella pianificazione e distribuzione del server perimetrale tipico che fornisce la Federazione.</span><span class="sxs-lookup"><span data-stu-id="3d13d-175">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="3d13d-176">America Online richiede che il certificato Edge Server assegnato al servizio Access Edge disponga di un utilizzo di chiave avanzata client (EKU).</span><span class="sxs-lookup"><span data-stu-id="3d13d-176">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a><span data-ttu-id="3d13d-177">Federazione XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="3d13d-177">Extensible Messaging and Presence Protocol (XMPP) Federation</span></span>

<span data-ttu-id="3d13d-178">Le versioni precedenti di Lync Server e Office Communications Server fornivano un gateway XMPP (Extensible Messaging and Presence Protocol) che poteva essere distribuito come ruolo server distinto per consentire la Federazione con le distribuzioni XMPP.</span><span class="sxs-lookup"><span data-stu-id="3d13d-178">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="3d13d-179">In Microsoft Lync Server 2013 la funzionalità XMPP può essere distribuita come caratteristica.</span><span class="sxs-lookup"><span data-stu-id="3d13d-179">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="3d13d-180">La funzionalità XMPP viene installata in due parti: un proxy XMPP che viene eseguito nel server perimetrale e il gateway XMPP che viene eseguito nei server front-end.</span><span class="sxs-lookup"><span data-stu-id="3d13d-180">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="3d13d-181">La distribuzione e la configurazione di XMPP sono descritte in [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) si prevede di supportare XMPP nella propria organizzazione definendo le regole di porta e protocollo nel firewall, la configurazione dei certificati e l'aggiunta di record DNS.</span><span class="sxs-lookup"><span data-stu-id="3d13d-181">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="3d13d-182">Gli argomenti seguenti in questa sezione riepilogano le informazioni che sarà necessario pianificare correttamente la Federazione XMPP per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3d13d-182">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="3d13d-183">La funzionalità XMPP di Lync Server 2013 è testata e supportata da Microsoft per la Federazione della messaggistica istantanea con Google Talk.</span><span class="sxs-lookup"><span data-stu-id="3d13d-183">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="3d13d-184">Per qualsiasi altro sistema XMPP, contattare il fornitore di terze parti per verificare che supportino la Federazione con Lync Server 2013 e per eventuali suggerimenti per la distribuzione o la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="3d13d-184">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>


> [!IMPORTANT]
> <span data-ttu-id="3d13d-185">La Federazione XMPP non è supportata per gli utenti che partecipano a Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="3d13d-185">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="3d13d-186">Questo vale sia per vedere le informazioni sulla presenza che per scambiare messaggi di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="3d13d-186">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

</div>

<div id="sectionSection3" class="section">

<span data-ttu-id="3d13d-187">Negli argomenti seguenti sono disponibili indicazioni per la definizione di certificati, porte del firewall e voci DNS per i tipi di scenari federativi supportati.</span><span class="sxs-lookup"><span data-stu-id="3d13d-187">In the following topics contain guidance for defining certificates, firewall ports and DNS entries for the types of supported federation scenarios.</span></span>

  - <span></span>  
    [<span data-ttu-id="3d13d-188">Riepilogo del certificato-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d13d-188">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="3d13d-189">Riepilogo della porta-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d13d-189">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="3d13d-190">Riepilogo DNS-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d13d-190">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3d13d-191">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d13d-191">See Also</span></span>


[<span data-ttu-id="3d13d-192">Configurare criteri per controllare l'accesso utente federato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d13d-192">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="3d13d-193">Scenari per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d13d-193">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="3d13d-194">Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d13d-194">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="3d13d-195">Determinare i requisiti di DNS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d13d-195">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="3d13d-196">Gestire la configurazione Access Edge per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d13d-196">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="3d13d-197">Gestire i domini federati SIP per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d13d-197">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="3d13d-198">Gestire i provider federati SIP per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d13d-198">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

