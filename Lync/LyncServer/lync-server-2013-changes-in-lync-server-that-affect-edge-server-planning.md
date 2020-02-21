---
title: 'Lync Server 2013: modifiche in Lync Server che influiscono sulla pianificazione del server perimetrale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2903bd2701ac860232dd73342ed280688feac34b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a><span data-ttu-id="ded8c-102">Modifiche apportate in Lync Server 2013 che influiscono sulla pianificazione del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ded8c-102">Changes in Lync Server 2013 that affect Edge Server planning</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ded8c-103">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="ded8c-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="ded8c-104">Lync Server 2013 introduce nuove funzionalità che estendono le funzionalità e i metodi di comunicazione per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="ded8c-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="ded8c-105">Inoltre, Lync Server 2013 introduce modifiche ai servizi esistenti per migliorare l'integrazione e l'estensione dei servizi disponibili per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ded8c-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="ded8c-106">Di seguito è riportato un riepilogo delle modifiche che possono influire sulla pianificazione e la distribuzione dei servizi server perimetrali di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ded8c-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

<div>

## <a name="support-for-ipv6-addressing"></a><span data-ttu-id="ded8c-107">Supporto dell'indirizzamento IPv6</span><span class="sxs-lookup"><span data-stu-id="ded8c-107">Support for IPv6 Addressing</span></span>

<span data-ttu-id="ded8c-108">Lync Server 2013 supporta l'indirizzamento IPv6 per tutti i servizi server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="ded8c-108">Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="ded8c-109">Se sono stati forniti indirizzi IPv6 per le interfacce tramite la configurazione in Windows Server, è possibile utilizzare gli indirizzi IPv6 nella configurazione del server perimetrale tramite la configurazione degli indirizzi IP in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="ded8c-109">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span> <span data-ttu-id="ded8c-110">Inoltre, il protocollo XMPP (Extensible Messaging and Presence Protocol) supporta IPv6.</span><span class="sxs-lookup"><span data-stu-id="ded8c-110">Additionally, the extensible messaging and presence protocol (XMPP) supports IPv6.</span></span> <span data-ttu-id="ded8c-111">Non è necessaria alcuna configurazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="ded8c-111">No additional configuration is required.</span></span> <span data-ttu-id="ded8c-112">Se IPv6 è configurato nella topologia, XMPP utilizzerà IPv6 (se necessario).</span><span class="sxs-lookup"><span data-stu-id="ded8c-112">If IPv6 is configured in the topology, XMPP will use IPv6 (where required).</span></span>

<span data-ttu-id="ded8c-113">Un ulteriore requisito per il supporto di IPv6 in Lync Server 2013 consiste nel creare record del sistema di nomi di dominio per i record che devono essere individuati e risolti in un indirizzo IPv6.</span><span class="sxs-lookup"><span data-stu-id="ded8c-113">An added requirement to support IPv6 in Lync Server 2013 is to create domain name system records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="ded8c-114">Il sistema DNS IPv6 utilizza record host definiti **AAAA** e chiamati "quad-A".</span><span class="sxs-lookup"><span data-stu-id="ded8c-114">IPv6 DNS uses host records that are defined as **AAAA** and called “quad-A”.</span></span> <span data-ttu-id="ded8c-115">Gli altri tipi di record sono coerenti con le controparti IPv4.</span><span class="sxs-lookup"><span data-stu-id="ded8c-115">Other record types are consistent with their IPv4 counterparts.</span></span>

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a><span data-ttu-id="ded8c-116">Supporto della distribuzione del protocollo XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="ded8c-116">Support for Extensible Messaging and Presence Protocol (XMPP) Deployment</span></span>

<span data-ttu-id="ded8c-117">Server perimetrale introduce un proxy XMPP completamente integrato (distribuito sui server perimetrali) e un gateway XMPP (distribuito nei server front end).</span><span class="sxs-lookup"><span data-stu-id="ded8c-117">Edge Server introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway (deployed on your Front End Servers).</span></span> <span data-ttu-id="ded8c-118">È possibile distribuire la federazione XMPP come componente facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ded8c-118">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="ded8c-119">Aggiungendo e configurando il proxy XMPP e il gateway XMPP, è possibile consentire agli utenti di Microsoft Lync 2013 di aggiungere contatti da partner basati su XMPP per la messaggistica istantanea e la presenza.</span><span class="sxs-lookup"><span data-stu-id="ded8c-119">By adding and configuring the XMPP proxy and XMPP gateway, you can enable your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ded8c-120">Attualmente, i servizi XMPP nel server perimetrale offrono solo la messaggistica istantanea e la presenza tra i client di Lync Server e i contatti basati su XMPP.</span><span class="sxs-lookup"><span data-stu-id="ded8c-120">Currently, the XMPP services in Edge Server only provide IM and presence between Lync Server clients and XMPP-based contacts.</span></span> <span data-ttu-id="ded8c-121">Il protocollo XMPP, inoltre, è ospitato in un solo sito.</span><span class="sxs-lookup"><span data-stu-id="ded8c-121">Additionally, XMPP is hosted in only one site.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ded8c-p106">La funzionalità XMPP di Lync Server 2013 è testata e supportata da Microsoft per la federazione di messaggistica istantanea con Google Talk. Per altri sistemi XMPP, contattare il fornitore di terze parti per verificare l'eventuale supporto della federazione con Lync Server 2013 e per indicazioni per la distribuzione o la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="ded8c-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a><span data-ttu-id="ded8c-124">Supporto della distribuzione di certificati di autenticazione audio/video e di autenticazione server-server</span><span class="sxs-lookup"><span data-stu-id="ded8c-124">Support for Rolling Audio/Video Authentication and Server to Server Authentication Certificates</span></span>

<span data-ttu-id="ded8c-p107">I certificati vengono utilizzati per generare token rilasciati ai client e altri consumer del servizio di autenticazione A/V e per l'autenticazione server-server. Il certificato di autenticazione audio/video è di tipo *AudioVideoAuthentication* e il certificato di autenticazione server-server è di tipo *OAuthTokenIssuer*.</span><span class="sxs-lookup"><span data-stu-id="ded8c-p107">A certificate is used to generate tokens that are issued to clients and other consumers of the A/V Authentication service and for server to server authentication. The Audio/Video Authentication certificate is of type *AudioVideoAuthentication* and the Server to Server Authentication certificate is of type *OAuthTokenIssuer*.</span></span>

<span data-ttu-id="ded8c-p108">Per l'autenticazione audio/video, i token vengono utilizzati per autenticare le richieste di allocazione della porta e vengono memorizzati nella cache per un massimo di 8 ore, ovvero la durata predefinita del token. In condizioni operative normali, questo è un metodo molto affidabile per creare e distribuire il materiale di autenticazione ai consumer del servizio A/V. I certificati, tuttavia, hanno una durata definita e una data e ora di scadenza prestabilite, in base alla data di creazione e ai criteri applicati dall'Autorità di certificazione che ha creato il certificato, solitamente 2 anni per questo tipo di certificato. Alla scadenza del certificato, qualsiasi token creato dal certificato scaduto e memorizzato nella cache dai consumer diventa non valido. Qualsiasi tentativo di utilizzare un token creato con un certificato scaduto risulterebbe in errori di allocazione Media Relay e causerebbe l'interruzione di qualsiasi sessione audio/video corrente. A questo punto, il client dovrebbe acquisire un nuovo token creato da un certificato valido per riprendere le normali funzionalità audio e video.</span><span class="sxs-lookup"><span data-stu-id="ded8c-p108">For Audio/Video Authentication, tokens are used to authenticate port allocation requests, and the tokens are cached for up to 8 hours – the default lifetime of the token. Under normal operation, this is a very reliable method to create and distribute authentication material to the A/V consumers. However, certificates have a finite lifetime and expire on a predefined date and time (based on creation date and the policies enforced at the certification authority that created the certificate, typically 2 years for this type of certificate). When the certificate expires, any tokens created by the expired certificate and cached by consumers become not valid. Any attempts to use a token created with an expired certificate would result in failed Media Relay allocations and any current Audio/Video sessions will fail. The client would need to acquire a new token created by a valid certificate to resume normal Audio and Video functionality.</span></span>

<span data-ttu-id="ded8c-133">L'autenticazione da server a server è gestita da un certificato globale richiesto e applicato a tutti i server della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ded8c-133">Server to Server Authentication is managed by a global certificate that is requested and applied to all servers in the deployment.</span></span> <span data-ttu-id="ded8c-134">Il certificato è responsabile dell'autenticazione dei server in Lync Server 2013, nonché dell'autenticazione in Exchange 2013 e Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ded8c-134">The certificate is responsible for authenticating servers in Lync Server 2013 as well as authenticating to Exchange 2013 and Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="ded8c-135">Per ulteriori informazioni sul funzionamento dell'autenticazione da server a server, vedere [Managing server-to-Server Authentication (OAuth) and partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span><span class="sxs-lookup"><span data-stu-id="ded8c-135">For more information on how Server to Server Authentication works, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span></span> <span data-ttu-id="ded8c-136">Una differenza molto importante tra il processo di autenticazione audio/video e il processo di autenticazione da server a server è la durata dell'autenticazione o dei token.</span><span class="sxs-lookup"><span data-stu-id="ded8c-136">One very important difference between the Audio/Video Authentication process and the Server to Server Authentication process is the lifetime of the authentication, or tokens.</span></span> <span data-ttu-id="ded8c-137">Per l'autenticazione audio/video, l'autenticazione scade dopo otto ore.</span><span class="sxs-lookup"><span data-stu-id="ded8c-137">For Audio/Video Authentication, the authentication expires after eight hours.</span></span> <span data-ttu-id="ded8c-138">L'autenticazione da server a server ha una durata di 24 ore.</span><span class="sxs-lookup"><span data-stu-id="ded8c-138">Server-to-Server Authentication has a lifetime of 24 hours.</span></span> <span data-ttu-id="ded8c-139">È necessario pianificare di conseguenza per ognuno dei tipi di certificato.</span><span class="sxs-lookup"><span data-stu-id="ded8c-139">You must plan accordingly for each of the certificate types.</span></span>

<span data-ttu-id="ded8c-140">New for Lync Server 2013 è la possibilità di eseguire il passaggio di un certificato di autenticazione audio/video sostitutivo e del certificato di autenticazione da server a server in anticipo rispetto alla scadenza del certificato corrente.</span><span class="sxs-lookup"><span data-stu-id="ded8c-140">New for Lync Server 2013 is the ability to stage a replacement Audio/Video Authentication certificate and Server to Server Authentication certificate in advance of the expiration of the current certificate.</span></span> <span data-ttu-id="ded8c-141">Il nuovo certificato viene quindi utilizzato per la generazione di nuovi token o di nuove richieste di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="ded8c-141">The new certificate is then used for generating new tokens or new authentication requests.</span></span> <span data-ttu-id="ded8c-142">Tuttavia, il certificato precedente viene mantenuto per la verifica delle sessioni e delle autenticazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="ded8c-142">but retains the old certificate for verifying the current sessions and authentications..</span></span> <span data-ttu-id="ded8c-143">Ciò che si ottiene è quello di prevenire efficacemente quasi tutti gli errori causati dalle scadenze dei token e dei certificati.</span><span class="sxs-lookup"><span data-stu-id="ded8c-143">What this accomplishes is to effectively prevent nearly all failures due to token and certificate expirations.</span></span> <span data-ttu-id="ded8c-144">Per informazioni dettagliate su questa funzionalità e su come configurarla, vedere [staging AV and OAuth Certificates in Lync Server 2013 using-roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span><span class="sxs-lookup"><span data-stu-id="ded8c-144">For details of this feature and how to configure it, see [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span></span>

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a><span data-ttu-id="ded8c-145">Minore dipendenza dall'affinità basata su cookie</span><span class="sxs-lookup"><span data-stu-id="ded8c-145">Reduced Reliance on Cookie-based Affinity</span></span>

<span data-ttu-id="ded8c-146">Nelle versioni precedenti di Lync Server e Office Communications Server, l'affinità basata su cookie veniva utilizzata dai servizi Web per garantire che lo stato della sessione dei servizi Web e del client venisse mantenuto.</span><span class="sxs-lookup"><span data-stu-id="ded8c-146">In previous versions of Lync Server and Office Communications Server, cookie-based affinity was used by the Web services to ensure that the client and Web services session state was maintained.</span></span> <span data-ttu-id="ded8c-147">I servizi Web di Lync Server 2013 utilizzano un meccanismo di affinità incorporato che consente di eliminare la maggior parte dei requisiti per l'affinità basata su cookie.</span><span class="sxs-lookup"><span data-stu-id="ded8c-147">Lync Server 2013 Web services use a built in affinity mechanism that eliminates most of the requirements for cookie-based affinity.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="ded8c-148">Il client Microsoft Lync 2010 mobile deve comunque utilizzare l'affinità basata su cookie e richiede la configurazione dell'affinità basata su cookie fino a quando non sono stati migrati tutti i client all'imminente client Microsoft Lync mobile (data di rilascio non ancora determinata).</span><span class="sxs-lookup"><span data-stu-id="ded8c-148">The Microsoft Lync 2010 Mobile client must still use cookie-based affinity and will require configuration of cookie-based affinity until you have migrated all clients to the upcoming Microsoft Lync Mobile client (Date of release not yet determined).</span></span>



</div>

<span data-ttu-id="ded8c-149">Per informazioni dettagliate sull'affinità basata su cookie in Lync Server 2013, vedere [componenti necessari per l'accesso degli utenti esterni in Lync server 2013](lync-server-2013-components-required-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="ded8c-149">For details about cookie-based affinity in Lync Server 2013, see [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

</div>

<div>

## <a name="autodiscover-enhancements"></a><span data-ttu-id="ded8c-150">Miglioramenti dell'individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="ded8c-150">AutoDiscover Enhancements</span></span>

<span data-ttu-id="ded8c-151">La funzionalità di individuazione automatica in Lync Server 2013 consente ai client di individuare altre funzionalità rese disponibili per la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="ded8c-151">The autodiscover feature in Lync Server 2013 enables clients to locate additional features that are made available for communication.</span></span> <span data-ttu-id="ded8c-152">La funzionalità di individuazione automatica è stata introdotta per la prima volta nell'aggiornamento cumulativo per Lync Server 2010: novembre 2011 per dispositivi mobili e Microsoft Lync 2010 mobile.</span><span class="sxs-lookup"><span data-stu-id="ded8c-152">Autodiscover was first introduced in the cumulative update for Lync Server 2010: November 2011 for Mobility and Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="ded8c-153">La funzionalità di individuazione automatica, nota anche per i nomi dei record DNS LyncDiscover e LyncDiscoverInternal, consente ai client di individuare e utilizzare i servizi per dispositivi mobili (per i client Microsoft Lync 2010 Mobile), Microsoft Lync Web App e l'utilità di pianificazione Web di Lync, nonché comunicazioni con Microsoft Exchange Server e SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="ded8c-153">The autodiscover feature (also known by the DNS record names LyncDiscover and LyncDiscoverInternal) allows clients to locate and use mobility services (for Microsoft Lync 2010 Mobile clients), the Microsoft Lync Web App, and the Lync Web scheduler, as well as communications with Microsoft Exchange Server and SharePoint Server.</span></span> <span data-ttu-id="ded8c-154">L'individuazione automatica viene installata come normale parte dell'installazione e della distribuzione dell'infrastruttura e dei server Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ded8c-154">Autodiscover is installed as normal part of the setup and deployment of your infrastructure and Lync Server 2013 servers.</span></span> <span data-ttu-id="ded8c-155">Il generatore di topologie e la distribuzione guidata di Lync Server eliminano la maggior parte delle attività di configurazione necessarie per l'aggiornamento cumulativo per Lync Server 2010: novembre 2011.</span><span class="sxs-lookup"><span data-stu-id="ded8c-155">The Topology Builder and Lync Server Deployment Wizard eliminate most of the configuration tasks that were required in cumulative update for Lync Server 2010: November 2011.</span></span>

</div>

<div>

## <a name="services-for-mobile-clients"></a><span data-ttu-id="ded8c-156">Servizi per i client mobili</span><span class="sxs-lookup"><span data-stu-id="ded8c-156">Services for Mobile Clients</span></span>

<span data-ttu-id="ded8c-157">Introdotti nell'aggiornamento cumulativo per Lync Server 2010: novembre 2011, i servizi per dispositivi mobili in Lync Server 2013 consentono ai telefoni mobili che eseguono Lync mobile e i dispositivi tablet che utilizzano il dispositivo mobile Apple iOS, Android, Windows Phone o Nokia per eseguire attività quali l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza.</span><span class="sxs-lookup"><span data-stu-id="ded8c-157">Introduced in the cumulative update for Lync Server 2010: November 2011, mobility services in Lync Server 2013 enable mobile phones running Lync Mobile and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="ded8c-158">Inoltre, i dispositivi mobili supportano alcune funzionalità di VoIP aziendale, ad esempio la partecipazione con un clic, Chiamata tramite ufficio, numero unico, segreteria telefonica e notifica delle chiamate senza risposta.</span><span class="sxs-lookup"><span data-stu-id="ded8c-158">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ded8c-159">I servizi di mobilità utilizzano il proxy inverso e i servizi pubblicati distribuiti nel Front End Server.</span><span class="sxs-lookup"><span data-stu-id="ded8c-159">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="ded8c-160">Non sono necessarie modifiche per i server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="ded8c-160">No changes are required to Edge Servers.</span></span> <span data-ttu-id="ded8c-161">È necessario almeno in uscita SIP/TCP/5061from il server che esegue il servizio Access Edge di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ded8c-161">Minimally you need outbound SIP/TCP/5061from the server running the Lync Server Access Edge service.</span></span>



</div>

</div>

<div>

## <a name="director-role-is-optional"></a><span data-ttu-id="ded8c-162">Il ruolo Director è facoltativo</span><span class="sxs-lookup"><span data-stu-id="ded8c-162">Director Role is Optional</span></span>

<span data-ttu-id="ded8c-163">Il ruolo del server Director nella topologia di Lync Server 2013 non è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="ded8c-163">The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="ded8c-164">Ospita ancora servizi Web, preautentica le richieste degli utenti in arrivo e indirizza gli utenti esterni al proprio pool Home.</span><span class="sxs-lookup"><span data-stu-id="ded8c-164">It still hosts web services, preauthenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="ded8c-165">Se si modifica il server Director da un ruolo consigliato a un ruolo facoltativo, Microsoft non intenderà diminuire il valore del server Director.</span><span class="sxs-lookup"><span data-stu-id="ded8c-165">By changing the Director from a recommended role to an optional role, Microsoft does not intend to diminish the value of the Director.</span></span> <span data-ttu-id="ded8c-166">L'intenzione è quella di ridurre il numero di server e altri requisiti hardware, ad esempio i servizi di bilanciamento del carico hardware per il Director, senza compromettere caratteristiche e funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ded8c-166">The intention is to reduce server count and other hardware requirements (for example, hardware load balancers for the Director) without compromising features and functionality.</span></span> <span data-ttu-id="ded8c-167">Poiché i Front End Server possono eseguire lo stesso processo del Director senza alcun impatto sui servizi forniti, è possibile distribuire i direttori se lo si sceglie.</span><span class="sxs-lookup"><span data-stu-id="ded8c-167">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can deploy Directors if you choose to.</span></span> <span data-ttu-id="ded8c-168">È possibile escludere in modo sicuro il Director con la sicurezza che i Front End Server forniranno gli stessi servizi al posto di un Director.</span><span class="sxs-lookup"><span data-stu-id="ded8c-168">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in place of a Director.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

