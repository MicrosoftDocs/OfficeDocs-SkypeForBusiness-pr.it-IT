---
title: 'Lync Server 2013: Modifiche introdotte in Lync Server che incidono sulla pianificazione dei server perimetrali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71d13b40430455c87a60c0fadc20980df5a8aa1b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a><span data-ttu-id="5e619-102">Modifiche introdotte in Lync Server 2013 che incidono sulla pianificazione dei server perimetrali</span><span class="sxs-lookup"><span data-stu-id="5e619-102">Changes in Lync Server 2013 that affect Edge Server planning</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e619-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="5e619-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="5e619-104">Lync Server 2013 introduce nuove funzionalità che estendono le caratteristiche e i metodi di comunicazione per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="5e619-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="5e619-105">Inoltre, Lync Server 2013 introduce le modifiche ai servizi esistenti per integrare meglio ed estendere i servizi disponibili per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5e619-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="5e619-106">Di seguito è riportato un riepilogo delle modifiche che possono influenzare la pianificazione e la distribuzione dei servizi di Lync Server 2013 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="5e619-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

<div>

## <a name="support-for-ipv6-addressing"></a><span data-ttu-id="5e619-107">Supporto per l'indirizzamento IPv6</span><span class="sxs-lookup"><span data-stu-id="5e619-107">Support for IPv6 Addressing</span></span>

<span data-ttu-id="5e619-108">Lync Server 2013 supporta l'indirizzamento IPv6 per tutti i servizi Edge Server.</span><span class="sxs-lookup"><span data-stu-id="5e619-108">Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="5e619-109">Se sono stati forniti indirizzi IPv6 per le interfacce tramite la configurazione in Windows Server, è possibile usare gli indirizzi IPv6 nella configurazione del server perimetrale tramite la configurazione degli indirizzi IP in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="5e619-109">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span> <span data-ttu-id="5e619-110">Inoltre, il protocollo XMPP (Extensible Messaging and Presence Protocol) supporta IPv6.</span><span class="sxs-lookup"><span data-stu-id="5e619-110">Additionally, the extensible messaging and presence protocol (XMPP) supports IPv6.</span></span> <span data-ttu-id="5e619-111">Non è necessaria alcuna configurazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="5e619-111">No additional configuration is required.</span></span> <span data-ttu-id="5e619-112">Se IPv6 è configurato nella topologia, XMPP userà IPv6 (dove richiesto).</span><span class="sxs-lookup"><span data-stu-id="5e619-112">If IPv6 is configured in the topology, XMPP will use IPv6 (where required).</span></span>

<span data-ttu-id="5e619-113">Un requisito aggiuntivo per supportare IPv6 in Lync Server 2013 consiste nel creare record di sistema di nomi di dominio per i record che devono essere individuati e risolti in un indirizzo IPv6.</span><span class="sxs-lookup"><span data-stu-id="5e619-113">An added requirement to support IPv6 in Lync Server 2013 is to create domain name system records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="5e619-114">DNS IPv6 usa i record host definiti come **aaaa** e detti "Quad-A".</span><span class="sxs-lookup"><span data-stu-id="5e619-114">IPv6 DNS uses host records that are defined as **AAAA** and called “quad-A”.</span></span> <span data-ttu-id="5e619-115">Altri tipi di record sono coerenti con le rispettive controparti IPv4.</span><span class="sxs-lookup"><span data-stu-id="5e619-115">Other record types are consistent with their IPv4 counterparts.</span></span>

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a><span data-ttu-id="5e619-116">Supporto per la distribuzione XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="5e619-116">Support for Extensible Messaging and Presence Protocol (XMPP) Deployment</span></span>

<span data-ttu-id="5e619-117">Edge Server introduce un proxy XMPP completamente integrato (distribuito sugli Edge Server) e un gateway XMPP (distribuito nei server front-end).</span><span class="sxs-lookup"><span data-stu-id="5e619-117">Edge Server introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway (deployed on your Front End Servers).</span></span> <span data-ttu-id="5e619-118">Puoi distribuire la Federazione XMPP come componente facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5e619-118">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="5e619-119">Aggiungendo e configurando il proxy XMPP e il gateway XMPP, è possibile consentire agli utenti di Microsoft Lync 2013 di aggiungere contatti da partner basati su XMPP per la messaggistica istantanea e la presenza.</span><span class="sxs-lookup"><span data-stu-id="5e619-119">By adding and configuring the XMPP proxy and XMPP gateway, you can enable your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5e619-120">Attualmente, i servizi XMPP in Edge Server consentono solo la messaggistica istantanea e la presenza tra i client Lync Server e i contatti basati su XMPP.</span><span class="sxs-lookup"><span data-stu-id="5e619-120">Currently, the XMPP services in Edge Server only provide IM and presence between Lync Server clients and XMPP-based contacts.</span></span> <span data-ttu-id="5e619-121">Inoltre, XMPP è ospitato in un solo sito.</span><span class="sxs-lookup"><span data-stu-id="5e619-121">Additionally, XMPP is hosted in only one site.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5e619-122">La funzionalità XMPP di Lync Server 2013 è testata e supportata da Microsoft per la Federazione della messaggistica istantanea con Google Talk.</span><span class="sxs-lookup"><span data-stu-id="5e619-122">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="5e619-123">Per qualsiasi altro sistema XMPP, contattare il fornitore di terze parti per verificare che supportino la Federazione con Lync Server 2013 e per eventuali suggerimenti per la distribuzione o la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="5e619-123">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a><span data-ttu-id="5e619-124">Supporto per l'autenticazione audio/video e i certificati di autenticazione server e server</span><span class="sxs-lookup"><span data-stu-id="5e619-124">Support for Rolling Audio/Video Authentication and Server to Server Authentication Certificates</span></span>

<span data-ttu-id="5e619-125">Viene usato un certificato per generare i token emessi ai client e ad altri utenti del servizio di autenticazione A/V e per l'autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="5e619-125">A certificate is used to generate tokens that are issued to clients and other consumers of the A/V Authentication service and for server to server authentication.</span></span> <span data-ttu-id="5e619-126">Il certificato di autenticazione audio/video è di tipo *AudioVideoAuthentication* e il certificato di autenticazione server-server è di tipo *OAuthTokenIssuer*.</span><span class="sxs-lookup"><span data-stu-id="5e619-126">The Audio/Video Authentication certificate is of type *AudioVideoAuthentication* and the Server to Server Authentication certificate is of type *OAuthTokenIssuer*.</span></span>

<span data-ttu-id="5e619-127">Per l'autenticazione audio/video, i token vengono usati per autenticare le richieste di allocazione della porta e i token vengono memorizzati nella cache per un massimo di 8 ore, ovvero la durata predefinita del token.</span><span class="sxs-lookup"><span data-stu-id="5e619-127">For Audio/Video Authentication, tokens are used to authenticate port allocation requests, and the tokens are cached for up to 8 hours – the default lifetime of the token.</span></span> <span data-ttu-id="5e619-128">In funzionamento normale, si tratta di un metodo molto affidabile per creare e distribuire materiale di autenticazione ai consumer A/V.</span><span class="sxs-lookup"><span data-stu-id="5e619-128">Under normal operation, this is a very reliable method to create and distribute authentication material to the A/V consumers.</span></span> <span data-ttu-id="5e619-129">I certificati hanno tuttavia una durata limitata e scadono in una data e un'ora predefinite (in base alla data di creazione e ai criteri applicati all'autorità di certificazione che ha creato il certificato, in genere 2 anni per questo tipo di certificato).</span><span class="sxs-lookup"><span data-stu-id="5e619-129">However, certificates have a finite lifetime and expire on a predefined date and time (based on creation date and the policies enforced at the certification authority that created the certificate, typically 2 years for this type of certificate).</span></span> <span data-ttu-id="5e619-130">Quando il certificato scade, i token creati dal certificato scaduto e memorizzati nella cache dai consumatori diventano non validi.</span><span class="sxs-lookup"><span data-stu-id="5e619-130">When the certificate expires, any tokens created by the expired certificate and cached by consumers become not valid.</span></span> <span data-ttu-id="5e619-131">Qualsiasi tentativo di usare un token creato con un certificato scaduto comporterebbe l'assegnazione di allocazioni di relay multimediali non riuscite e le eventuali sessioni audio/video correnti avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5e619-131">Any attempts to use a token created with an expired certificate would result in failed Media Relay allocations and any current Audio/Video sessions will fail.</span></span> <span data-ttu-id="5e619-132">Il client dovrà acquisire un nuovo token creato da un certificato valido per riprendere le normali funzionalità audio e video.</span><span class="sxs-lookup"><span data-stu-id="5e619-132">The client would need to acquire a new token created by a valid certificate to resume normal Audio and Video functionality.</span></span>

<span data-ttu-id="5e619-133">L'autenticazione da server a server è gestita da un certificato globale richiesto e applicato a tutti i server della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5e619-133">Server to Server Authentication is managed by a global certificate that is requested and applied to all servers in the deployment.</span></span> <span data-ttu-id="5e619-134">Il certificato è responsabile per l'autenticazione dei server in Lync Server 2013 e per l'autenticazione in Exchange 2013 e Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e619-134">The certificate is responsible for authenticating servers in Lync Server 2013 as well as authenticating to Exchange 2013 and Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="5e619-135">Per altre informazioni sul funzionamento dell'autenticazione da server a server, vedere [gestione dell'autenticazione server-Server (OAuth) e delle applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span><span class="sxs-lookup"><span data-stu-id="5e619-135">For more information on how Server to Server Authentication works, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span></span> <span data-ttu-id="5e619-136">Una differenza molto importante tra il processo di autenticazione audio/video e il processo di autenticazione da server a server è la durata dell'autenticazione o dei token.</span><span class="sxs-lookup"><span data-stu-id="5e619-136">One very important difference between the Audio/Video Authentication process and the Server to Server Authentication process is the lifetime of the authentication, or tokens.</span></span> <span data-ttu-id="5e619-137">Per l'autenticazione audio/video, l'autenticazione scade dopo otto ore.</span><span class="sxs-lookup"><span data-stu-id="5e619-137">For Audio/Video Authentication, the authentication expires after eight hours.</span></span> <span data-ttu-id="5e619-138">L'autenticazione da server a server ha una durata di 24 ore.</span><span class="sxs-lookup"><span data-stu-id="5e619-138">Server-to-Server Authentication has a lifetime of 24 hours.</span></span> <span data-ttu-id="5e619-139">È necessario pianificare di conseguenza ogni tipo di certificato.</span><span class="sxs-lookup"><span data-stu-id="5e619-139">You must plan accordingly for each of the certificate types.</span></span>

<span data-ttu-id="5e619-140">Novità di Lync Server 2013 è la possibilità di eseguire la fase di sostituzione del certificato di autenticazione audio/video e del server al certificato di autenticazione server in anticipo rispetto alla scadenza del certificato corrente.</span><span class="sxs-lookup"><span data-stu-id="5e619-140">New for Lync Server 2013 is the ability to stage a replacement Audio/Video Authentication certificate and Server to Server Authentication certificate in advance of the expiration of the current certificate.</span></span> <span data-ttu-id="5e619-141">Il nuovo certificato viene quindi usato per generare nuovi token o nuove richieste di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="5e619-141">The new certificate is then used for generating new tokens or new authentication requests.</span></span> <span data-ttu-id="5e619-142">conserva però il vecchio certificato per la verifica delle sessioni e delle autenticazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="5e619-142">but retains the old certificate for verifying the current sessions and authentications..</span></span> <span data-ttu-id="5e619-143">Il risultato è quello di impedire in modo efficace quasi tutti gli errori dovuti alla scadenza del token e del certificato.</span><span class="sxs-lookup"><span data-stu-id="5e619-143">What this accomplishes is to effectively prevent nearly all failures due to token and certificate expirations.</span></span> <span data-ttu-id="5e619-144">Per informazioni dettagliate su questa funzionalità e su come configurarla, vedere [staging di certificati AV e OAuth in Lync Server 2013 con-roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span><span class="sxs-lookup"><span data-stu-id="5e619-144">For details of this feature and how to configure it, see [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span></span>

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a><span data-ttu-id="5e619-145">Dipendenza ridotta dall'affinità basata su cookie</span><span class="sxs-lookup"><span data-stu-id="5e619-145">Reduced Reliance on Cookie-based Affinity</span></span>

<span data-ttu-id="5e619-146">Nelle versioni precedenti di Lync Server e Office Communications Server l'affinità basata su cookie è stata usata dai servizi Web per assicurarsi che lo stato della sessione client e servizi Web sia stato mantenuto.</span><span class="sxs-lookup"><span data-stu-id="5e619-146">In previous versions of Lync Server and Office Communications Server, cookie-based affinity was used by the Web services to ensure that the client and Web services session state was maintained.</span></span> <span data-ttu-id="5e619-147">I servizi Web di Lync Server 2013 usano un meccanismo di affinità incorporato che elimina la maggior parte dei requisiti per l'affinità basata su cookie.</span><span class="sxs-lookup"><span data-stu-id="5e619-147">Lync Server 2013 Web services use a built in affinity mechanism that eliminates most of the requirements for cookie-based affinity.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="5e619-148">Il client per dispositivi mobili Microsoft Lync 2010 deve comunque usare l'affinità basata su cookie e richiederà la configurazione dell'affinità basata su cookie finché non si esegue la migrazione di tutti i client al client Microsoft Lync Mobile imminente (data di rilascio non ancora determinato).</span><span class="sxs-lookup"><span data-stu-id="5e619-148">The Microsoft Lync 2010 Mobile client must still use cookie-based affinity and will require configuration of cookie-based affinity until you have migrated all clients to the upcoming Microsoft Lync Mobile client (Date of release not yet determined).</span></span>



</div>

<span data-ttu-id="5e619-149">Per informazioni dettagliate sull'affinità basata su cookie in Lync Server 2013, vedere [componenti necessari per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-components-required-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="5e619-149">For details about cookie-based affinity in Lync Server 2013, see [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

</div>

<div>

## <a name="autodiscover-enhancements"></a><span data-ttu-id="5e619-150">Miglioramenti per l'individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="5e619-150">AutoDiscover Enhancements</span></span>

<span data-ttu-id="5e619-151">La caratteristica di individuazione automatica in Lync Server 2013 consente ai client di individuare funzionalità aggiuntive messe a disposizione per la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="5e619-151">The autodiscover feature in Lync Server 2013 enables clients to locate additional features that are made available for communication.</span></span> <span data-ttu-id="5e619-152">L'individuazione automatica è stata introdotta per la prima volta nell'aggiornamento cumulativo per Lync Server 2010: novembre 2011 per la mobilità e Microsoft Lync 2010 mobile.</span><span class="sxs-lookup"><span data-stu-id="5e619-152">Autodiscover was first introduced in the cumulative update for Lync Server 2010: November 2011 for Mobility and Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="5e619-153">La caratteristica di individuazione automatica (nota anche con i nomi dei record DNS LyncDiscover e LyncDiscoverInternal) consente ai client di individuare e usare i servizi di mobilità (per i client mobili Microsoft Lync 2010), Microsoft Lync Web App e Lync Web Scheduler, nonché comunicazioni con Microsoft Exchange Server e SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="5e619-153">The autodiscover feature (also known by the DNS record names LyncDiscover and LyncDiscoverInternal) allows clients to locate and use mobility services (for Microsoft Lync 2010 Mobile clients), the Microsoft Lync Web App, and the Lync Web scheduler, as well as communications with Microsoft Exchange Server and SharePoint Server.</span></span> <span data-ttu-id="5e619-154">L'individuazione automatica viene installata come normale parte della configurazione e della distribuzione dell'infrastruttura e dei server di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e619-154">Autodiscover is installed as normal part of the setup and deployment of your infrastructure and Lync Server 2013 servers.</span></span> <span data-ttu-id="5e619-155">Il generatore di topologia e la distribuzione guidata di Lync Server eliminano la maggior parte delle attività di configurazione necessarie in aggiornamento cumulativo per Lync Server 2010: novembre 2011.</span><span class="sxs-lookup"><span data-stu-id="5e619-155">The Topology Builder and Lync Server Deployment Wizard eliminate most of the configuration tasks that were required in cumulative update for Lync Server 2010: November 2011.</span></span>

</div>

<div>

## <a name="services-for-mobile-clients"></a><span data-ttu-id="5e619-156">Servizi per i client mobili</span><span class="sxs-lookup"><span data-stu-id="5e619-156">Services for Mobile Clients</span></span>

<span data-ttu-id="5e619-157">Introdotta nell'aggiornamento cumulativo per Lync Server 2010: novembre 2011, servizi di mobilità in Lync Server 2013 abilitare i telefoni cellulari che eseguono Lync mobile e tablet usando i dispositivi mobili Apple iOS, Android, Windows Phone o Nokia da eseguire attività come l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza.</span><span class="sxs-lookup"><span data-stu-id="5e619-157">Introduced in the cumulative update for Lync Server 2010: November 2011, mobility services in Lync Server 2013 enable mobile phones running Lync Mobile and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="5e619-158">I dispositivi mobili supportano inoltre alcune funzionalità VoIP aziendale, ad esempio fare clic per partecipare a una conferenza, chiamare tramite lavoro, raggiungere un numero singolo, la segreteria telefonica e la notifica delle chiamate perse.</span><span class="sxs-lookup"><span data-stu-id="5e619-158">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5e619-159">I servizi di mobilità usano il proxy inverso e i servizi pubblicati distribuiti nei server front-end.</span><span class="sxs-lookup"><span data-stu-id="5e619-159">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="5e619-160">Per Edge Server non sono necessarie modifiche.</span><span class="sxs-lookup"><span data-stu-id="5e619-160">No changes are required to Edge Servers.</span></span> <span data-ttu-id="5e619-161">È necessario un collegamento SIP/TCP/5061from in uscita nel server che gestisce il servizio Access Edge di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5e619-161">Minimally you need outbound SIP/TCP/5061from the server running the Lync Server Access Edge service.</span></span>



</div>

</div>

<div>

## <a name="director-role-is-optional"></a><span data-ttu-id="5e619-162">Il ruolo Director è facoltativo</span><span class="sxs-lookup"><span data-stu-id="5e619-162">Director Role is Optional</span></span>

<span data-ttu-id="5e619-163">Il ruolo del server Director nella topologia di Lync Server 2013 non è cambiato.</span><span class="sxs-lookup"><span data-stu-id="5e619-163">The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="5e619-164">Ospita ancora servizi Web, esegue la preautenticazione delle richieste utente in arrivo e indirizza gli utenti esterni al proprio pool Home.</span><span class="sxs-lookup"><span data-stu-id="5e619-164">It still hosts web services, preauthenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="5e619-165">Modificando il Director da un ruolo consigliato a un ruolo facoltativo, Microsoft non intenderà diminuire il valore del Director.</span><span class="sxs-lookup"><span data-stu-id="5e619-165">By changing the Director from a recommended role to an optional role, Microsoft does not intend to diminish the value of the Director.</span></span> <span data-ttu-id="5e619-166">L'intenzione consiste nel ridurre il numero di server e altri requisiti hardware, ad esempio i servizi di bilanciamento del carico hardware per il Director, senza compromettere caratteristiche e funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5e619-166">The intention is to reduce server count and other hardware requirements (for example, hardware load balancers for the Director) without compromising features and functionality.</span></span> <span data-ttu-id="5e619-167">Dato che i server front-end possono eseguire lo stesso processo di Director senza alcun impatto sui servizi forniti, è possibile distribuire direttori se si sceglie di.</span><span class="sxs-lookup"><span data-stu-id="5e619-167">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can deploy Directors if you choose to.</span></span> <span data-ttu-id="5e619-168">È possibile escludere in modo sicuro il Director con sicurezza che i server front-end forniranno gli stessi servizi al posto di un amministratore.</span><span class="sxs-lookup"><span data-stu-id="5e619-168">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in place of a Director.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

