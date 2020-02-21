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
ms.openlocfilehash: c1e31e9fd0de6135dd1fd3f552d0d692f1bf7543
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="e2320-102">Pianificazione per SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2320-102">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2320-103">_**Ultimo argomento modificato:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="e2320-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="e2320-104">I server perimetrali possono essere configurati in modo da consentire agli utenti interni ed esterni di accedere ai contatti in organizzazioni o servizi partner.</span><span class="sxs-lookup"><span data-stu-id="e2320-104">Edge Servers can be configured to allow your internal and external users access to contacts at partner organizations or services.</span></span> <span data-ttu-id="e2320-105">Le federazioni, ovvero questi accordi tra partner, possono rendere disponibile qualsiasi contatto dell'organizzazione alla federazione partner e viceversa:</span><span class="sxs-lookup"><span data-stu-id="e2320-105">Federations, as these partner agreements are known, can provide any or all of the following to the contacts in your organization on the partner federation or contacts in the partner federation to yours:</span></span>

  - <span data-ttu-id="e2320-106">Messaggistica istantanea e presenza</span><span class="sxs-lookup"><span data-stu-id="e2320-106">Instant messaging and presence</span></span>

  - <span data-ttu-id="e2320-107">Collaborazione e servizi di conferenza, ad esempio Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="e2320-107">Collaboration and conferencing, for example – Web conferencing</span></span>

  - <span data-ttu-id="e2320-108">Conferenze audio, video o entrambe</span><span class="sxs-lookup"><span data-stu-id="e2320-108">Audio conferencing, video conferencing, or both</span></span>

<span data-ttu-id="e2320-109">In alcuni casi, la comunicazione, ad esempio la messaggistica istantanea e la presenza tra un contatto Microsoft Lync Server 2013 e un protocollo XMPP (Extensible Messaging and Presence Protocol), è solo di supporto peer-to-peer-che supporta solo l'utente e il contatto a livello federato. partner.</span><span class="sxs-lookup"><span data-stu-id="e2320-109">In some cases the communication, for example instant messaging (IM) and presence between a Microsoft Lync Server 2013 and an extensible messaging and presence protocol (XMPP) contact, is peer-to-peer only - supporting only you and the contact at the federated partner.</span></span> <span data-ttu-id="e2320-110">In altri casi, ad esempio Lync Server, Lync Server 2010 alla federazione Lync Server 2013, è possibile invitare più partecipanti a partecipare alla conversazione.</span><span class="sxs-lookup"><span data-stu-id="e2320-110">In other cases, such as a Lync Server, Lync Server 2010 to Lync Server 2013 federation, multiple participants can be invited to join into the conversation.</span></span>

<div>

## <a name="lync-server-and-office-communications-server-federation"></a><span data-ttu-id="e2320-111">Federazione di Lync Server e Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="e2320-111">Lync Server and Office Communications Server Federation</span></span>

<span data-ttu-id="e2320-112">La Federazione tra Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server supporta le comunicazioni peer-to-peer e multi-party.</span><span class="sxs-lookup"><span data-stu-id="e2320-112">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="e2320-113">È possibile effettuare l'escalation delle conversazioni peer-to-peer a conversazioni tra più parti, consentendo l'esecuzione di riunioni ad hoc.</span><span class="sxs-lookup"><span data-stu-id="e2320-113">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="e2320-114">Le riunioni, che possono essere conferenze Web o conferenze audio/video, possono essere pianificate in modo da includere contatti all'interno dell'organizzazione e contatti partner con cui si attua la federazione.</span><span class="sxs-lookup"><span data-stu-id="e2320-114">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="e2320-115">La Federazione è stata introdotta per la prima volta in Microsoft Office Live Communications Server 2005 e ha supportato un tipo di federazione, Direct Federation.</span><span class="sxs-lookup"><span data-stu-id="e2320-115">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="e2320-116">Direct Federation richiede di conoscere il dominio SIP (Session Initiation Protocol) del partner federativo e il nome di dominio completo (FQDN) del server perimetrale del partner.</span><span class="sxs-lookup"><span data-stu-id="e2320-116">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="e2320-117">In Live Communications Server 2005 con SP1 sono stati introdotti altri tipi di federazione, tutti i quali sono necessari record SRV DNS (Domain Name System) che devono essere pubblicati dal partner federato per individuare il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="e2320-117">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="e2320-118">La terminologia relativa a tale versione è stata la seguente:</span><span class="sxs-lookup"><span data-stu-id="e2320-118">The terminology for that release was:</span></span>

  - <span data-ttu-id="e2320-119">*Aprire Federazione avanzata*: accettare qualsiasi nome di dominio SIP e utilizzare DNS SRV per individuare il server perimetrale partner</span><span class="sxs-lookup"><span data-stu-id="e2320-119">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="e2320-120">*Federazione avanzata*: configurare il nome di dominio SIP del partner come partner federativo per l'organizzazione e utilizzare DNS SRV per trovare il server perimetrale del partner</span><span class="sxs-lookup"><span data-stu-id="e2320-120">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="e2320-121">*Federazione diretta*: configurare il nome di dominio SIP del partner e l'FQDN nel server perimetrale del partner</span><span class="sxs-lookup"><span data-stu-id="e2320-121">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="e2320-122">*Elenco Consenti server*: accettare qualsiasi dominio, utilizzare DNS SRV per individuare il server perimetrale di un provider di hosting o di un provider di connettività per la messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="e2320-122">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="e2320-123">Microsoft Office Communications Server 2007 ha introdotto la denominazione aggiornata per i tipi di federazione per definire meglio ciò che ogni tipo di Federazione ha effettivamente ottenuto:</span><span class="sxs-lookup"><span data-stu-id="e2320-123">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="e2320-124">La federazione avanzata aperta è stata denominata *dominio individuato del partner*.</span><span class="sxs-lookup"><span data-stu-id="e2320-124">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="e2320-125">La federazione avanzata è stata denominata *dominio partner consentito*.</span><span class="sxs-lookup"><span data-stu-id="e2320-125">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="e2320-126">La federazione diretta è stata denominata *server partner consentito*.</span><span class="sxs-lookup"><span data-stu-id="e2320-126">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="e2320-127">L'elenco dei server consentiti è stato denominato *provider di hosting* e *provider di servizi di messaggistica istantanea pubblica*.</span><span class="sxs-lookup"><span data-stu-id="e2320-127">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="e2320-128">Microsoft Lync Server 2010 ha introdotto una definizione più restrittiva del provider di hosting in conformità con Microsoft Lync Online 2010 e Microsoft Office 365 e ha anche reso soggetto allo stesso elenco consentito definito dal tipo di Federazione del dominio del partner consentito.</span><span class="sxs-lookup"><span data-stu-id="e2320-128">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="e2320-129">L'abilitazione della Federazione tra Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server utilizza i server perimetrali e i proxy inversi per applicare le regole e i domini partner consentiti definiti.</span><span class="sxs-lookup"><span data-stu-id="e2320-129">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="e2320-130">Da un punto di vista della pianificazione, la Federazione con altri Lync Server, Office Communications Server richiede quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e2320-130">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="e2320-131">Abilitare la federazione in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="e2320-131">Enable federation in Topology Builder.</span></span> <span data-ttu-id="e2320-132">Per informazioni dettagliate, vedere la sezione relativa alla distribuzione di [federazione SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="e2320-132">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="e2320-133">Determinare i propri requisiti per l'individuazione del dominio federato:</span><span class="sxs-lookup"><span data-stu-id="e2320-133">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="e2320-134">Per la configurazione manuale della Federazione, è necessario disporre del nome di dominio completo (FQDN) del server perimetrale e del nome di dominio del partner oppure del nome di dominio online, immesso nel pannello di controllo di Lync Server, nella **Federazione e nell'accesso esterno**, ovvero nei **domini federati SIP**.</span><span class="sxs-lookup"><span data-stu-id="e2320-134">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="e2320-135">Creare nuovi criteri facendo clic su **Nuovo** oppure modificare criteri esistenti facendo clic su **Modifica** in modo da consentire o bloccare i domini in base all'FQDN.</span><span class="sxs-lookup"><span data-stu-id="e2320-135">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="e2320-136">La configurazione manuale del server perimetrale di un partner federativo è soggetta a un errore nel caso in cui il partner modifichi l'indirizzo IP del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="e2320-136">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="e2320-137">Per i <STRONG>nuovi domini federati SIP</STRONG>, è necessario fornire il <STRONG>nome di dominio (o FQDN)</STRONG> per Microsoft Lync Online, Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2320-137">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="e2320-138">Per Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server è inoltre necessario fornire un <STRONG>servizio Access Edge (FQDN)</STRONG></span><span class="sxs-lookup"><span data-stu-id="e2320-138">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="e2320-139">Per la Federazione partner individuata, in cui i partner possono individuare il server perimetrale, è necessario creare un record \_SRV nel DNS esterno-sipfederationtls. \_TCP.contoso.com – che punta alla porta 5061 e al record host (A) del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e2320-139">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="e2320-140">Se si supportano client Microsoft Lync Mobile su Windows Phone o Apple iPhone, iPad o altri dispositivi Apple e si utilizza il servizio di notifica push o di notifica push, è necessario pianificare _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="e2320-140">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="e2320-141">&lt;Record SRV&gt; di dominio SIP per ogni dominio SIP di cui si dispone di client mobili di Lync.</span><span class="sxs-lookup"><span data-stu-id="e2320-141">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="e2320-142">Android e Nokia Symbian Lync mobile non utilizzano la notifica push e non sono soggetti a questo requisito.</span><span class="sxs-lookup"><span data-stu-id="e2320-142">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="e2320-143">Configurare criteri di accesso utenti esterni per il supporto dei domini federati.</span><span class="sxs-lookup"><span data-stu-id="e2320-143">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="e2320-144">Aprire le porte del firewall per il protocollo SIP (Session Initiation Protocol), le conferenze Web e le conferenze audio/video per supportare la federazione o i contatti abilitati.</span><span class="sxs-lookup"><span data-stu-id="e2320-144">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="e2320-145">Per informazioni dettagliate, vedere: [determinare i requisiti di porte e firewall a/V esterni per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="e2320-145">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="e2320-146">Le informazioni seguenti consentono di definire il certificato, il protocollo e i requisiti DNS per la Federazione con Microsoft Lync Server 2013 e Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e2320-146">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="e2320-147">La pianificazione per i certificati, i requisiti del firewall e del protocollo di trasporto e i requisiti DNS è in genere un processo diretto se sono stati pianificati o distribuiti i server perimetrali di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2320-147">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="e2320-148">Poiché la Federazione è una funzionalità aggiuntiva che utilizza il server perimetrale esistente, i requisiti di pianificazione vengono in genere soddisfatti dalla pianificazione e dalla distribuzione del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="e2320-148">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="e2320-149">È consigliabile utilizzare le tabelle seguenti per verificare che i requisiti vengano soddisfatti e apportare eventuali modifiche a porte/protocolli e DNS in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="e2320-149">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="e2320-150">Se si dispone di un pool di server perimetrali e si esegue la Federazione con i partner di Lync Server 2013 o Lync Server 2010, è possibile utilizzare il bilanciamento del carico DNS o i dispositivi di bilanciamento del carico hardware sui lati interni ed esterni dei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="e2320-150">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="e2320-151">Se si sta effettuando la Federazione con Office Communications Server 2007 o Office Communications Server 2007 R2, il bilanciamento del carico hardware fornirà supporto per il failover nel caso di un server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="e2320-151">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="e2320-152">Office Communications Server 2007 e Office Communications Server 2007 R2 non sono compatibili con il bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="e2320-152">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="e2320-153">I server perimetrali partner stabiliranno la comunicazione con il primo server perimetrale del pool che risponde.</span><span class="sxs-lookup"><span data-stu-id="e2320-153">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="e2320-154">Se il server perimetrale ha esito negativo, la comunicazione non esegue automaticamente il failover.</span><span class="sxs-lookup"><span data-stu-id="e2320-154">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="e2320-155">I requisiti dei certificati vengono in genere soddisfatti tramite la pianificazione di certificati per il server perimetrale o il piano server perimetrale scelto.</span><span class="sxs-lookup"><span data-stu-id="e2320-155">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a><span data-ttu-id="e2320-156">Connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="e2320-156">Public Instant Messaging Connectivity</span></span>

<span data-ttu-id="e2320-157">La connettività per la messaggistica istantanea pubblica è una classe di federazione ed è configurata per consentire agli utenti interni ed esterni di Lync Server 2013 di aggiungere contatti da uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="e2320-157">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="e2320-158">Contatti di Messenger</span><span class="sxs-lookup"><span data-stu-id="e2320-158">Messenger contacts</span></span>

  - <span data-ttu-id="e2320-159">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="e2320-159">Yahoo\!</span></span> <span data-ttu-id="e2320-160">contatti</span><span class="sxs-lookup"><span data-stu-id="e2320-160">contacts</span></span>

  - <span data-ttu-id="e2320-161">Contatti di AOL (America Online)</span><span class="sxs-lookup"><span data-stu-id="e2320-161">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="e2320-162">Al 1 ° settembre 2012, la licenza di sottoscrizione a Microsoft Lync Public IM Connectivity (PIC USL) non è più disponibile per l'acquisto dei contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="e2320-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="e2320-163">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="e2320-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="e2320-164">Messenger fino alla data di arresto del servizio (la data esatta deve ancora essere decisa, ma non prima del giugno 2013).</span><span class="sxs-lookup"><span data-stu-id="e2320-164">Messenger until the service shutdown date (exact date is still to be decided, but no sooner than June 2013).</span></span></P>
> <LI>
> <P><span data-ttu-id="e2320-165">Il PIC USL è una licenza di sottoscrizione per utente, per mese, necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="e2320-165">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="e2320-166">Messaggero.</span><span class="sxs-lookup"><span data-stu-id="e2320-166">Messenger.</span></span> <span data-ttu-id="e2320-167">La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale non verrà rinnovato.</span><span class="sxs-lookup"><span data-stu-id="e2320-167">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="e2320-168">Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="e2320-168">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="e2320-169">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="e2320-169">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="e2320-170">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone attraverso la messaggistica istantanea e la voce.</span><span class="sxs-lookup"><span data-stu-id="e2320-170">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="e2320-171">Per questa classe di federazione è necessario tenere conto delle considerazioni seguenti per la pianificazione:</span><span class="sxs-lookup"><span data-stu-id="e2320-171">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="e2320-172">Gli utenti di Windows Live Messenger possono avere comunicazioni audio/visive peer-to-peer con gli utenti di Lync Server 2013, oltre alla messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="e2320-172">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="e2320-173">I server perimetrali devono soddisfare requisiti specifici per le porte e i protocolli.</span><span class="sxs-lookup"><span data-stu-id="e2320-173">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="e2320-174">Per informazioni dettagliate, vedere [Determine External a/V firewall and Port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2320-174">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="e2320-175">La messaggistica istantanea Yahoo non ha requisiti univoci, oltre a quelli utilizzati in genere nella pianificazione e nella distribuzione del server perimetrale tipico che fornisce la Federazione.</span><span class="sxs-lookup"><span data-stu-id="e2320-175">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="e2320-176">America Online richiede che il certificato del server perimetrale assegnato al servizio Access Edge disponga di un utilizzo chiave avanzato (EKU, client Enhanced Key Usage).</span><span class="sxs-lookup"><span data-stu-id="e2320-176">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a><span data-ttu-id="e2320-177">Federazione del protocollo XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="e2320-177">Extensible Messaging and Presence Protocol (XMPP) Federation</span></span>

<span data-ttu-id="e2320-178">Le versioni precedenti di Lync Server e Office Communications Server fornivano un gateway XMPP (Extensible Messaging and Presence Protocol) che potrebbe essere distribuito come ruolo server separato per consentire la Federazione con le distribuzioni XMPP.</span><span class="sxs-lookup"><span data-stu-id="e2320-178">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="e2320-179">In Microsoft Lync Server 2013, la funzionalità XMPP può essere distribuita come caratteristica.</span><span class="sxs-lookup"><span data-stu-id="e2320-179">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="e2320-180">La funzionalità XMPP è installata in due parti: un proxy XMPP che viene eseguito nel server perimetrale e il gateway XMPP che viene eseguito nei Front End Server.</span><span class="sxs-lookup"><span data-stu-id="e2320-180">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="e2320-181">La distribuzione e la configurazione di XMPP sono descritte in [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) si prevede di supportare XMPP nell'organizzazione definendo le regole relative alle porte e ai protocolli del firewall, alla configurazione dei certificati e all'aggiunta di record DNS.</span><span class="sxs-lookup"><span data-stu-id="e2320-181">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="e2320-182">Negli argomenti seguenti di questa sezione vengono riepilogate le informazioni necessarie per pianificare correttamente la Federazione XMPP per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e2320-182">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="e2320-p120">La funzionalità XMPP di Lync Server 2013 è testata e supportata da Microsoft per la federazione di messaggistica istantanea con Google Talk. Per altri sistemi XMPP, contattare il fornitore di terze parti per verificare l'eventuale supporto della federazione con Lync Server 2013 e per indicazioni per la distribuzione o la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="e2320-p120">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>


> [!IMPORTANT]
> <span data-ttu-id="e2320-185">La Federazione XMPP non è supportata per gli utenti ospitati in Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="e2320-185">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="e2320-186">Ciò vale sia per la visualizzazione delle informazioni sulla presenza che per lo scambio di messaggi di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="e2320-186">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

</div>

<div id="sectionSection3" class="section">

<span data-ttu-id="e2320-187">Negli argomenti seguenti vengono fornite indicazioni per la definizione dei certificati, delle porte del firewall e delle voci DNS per i tipi di scenari di federazione supportati.</span><span class="sxs-lookup"><span data-stu-id="e2320-187">In the following topics contain guidance for defining certificates, firewall ports and DNS entries for the types of supported federation scenarios.</span></span>

  - <span></span>  
    [<span data-ttu-id="e2320-188">Riepilogo del certificato-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2320-188">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="e2320-189">Riepilogo delle porte-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2320-189">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="e2320-190">Riepilogo DNS-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2320-190">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e2320-191">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2320-191">See Also</span></span>


[<span data-ttu-id="e2320-192">Configurare criteri per controllare l'accesso degli utenti federati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2320-192">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="e2320-193">Scenari per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2320-193">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="e2320-194">Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2320-194">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="e2320-195">Determinare i requisiti DNS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2320-195">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="e2320-196">Gestire la configurazione di Access Edge per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2320-196">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="e2320-197">Gestire i domini federati SIP per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2320-197">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="e2320-198">Gestire i provider federati SIP per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2320-198">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

