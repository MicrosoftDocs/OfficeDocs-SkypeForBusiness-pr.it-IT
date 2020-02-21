---
title: 'Lync Server 2013: topologie e componenti per dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ccce5823e997cafc5e8c8e7555df18bc67d1fe6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a><span data-ttu-id="c42d4-102">Topologie e componenti per dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42d4-102">Topologies and components for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c42d4-103">_**Ultimo argomento modificato:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="c42d4-103">_**Topic Last Modified:** 2013-02-17_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="c42d4-104">Per supportare le applicazioni di Lync mobile nei dispositivi mobili, Lync Server 2013 offre tre servizi: Lync Server 2013 MCX Mobility Service, Lync Server 2013 Autodiscover Service e Lync Server 2013 Push Notification Service.</span><span class="sxs-lookup"><span data-stu-id="c42d4-104">To support Lync mobile applications on mobile devices, Lync Server 2013 provides three services: Lync Server 2013 Mcx Mobility Service, Lync Server 2013 Autodiscover Service, and Lync Server 2013 Push Notification Service.</span></span> <span data-ttu-id="c42d4-105">Gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 aggiunge un servizio gratuito, ma avanzato, per i client mobili di Lync 2013, ovvero il supporto per la mobilità tramite l'utilizzo di Unified Communications Web API o UCWA.</span><span class="sxs-lookup"><span data-stu-id="c42d4-105">The Cumulative Updates for Lync Server 2013: February 2013 adds a complimentary, but advanced, service for Lync 2013 Mobile clients—mobility support through the use of the Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="c42d4-106">In questa sezione vengono descritti brevemente i componenti e vengono identificate le topologie di Lync Server 2013 che supportano la mobilità.</span><span class="sxs-lookup"><span data-stu-id="c42d4-106">This section briefly describes these components and identifies the Lync Server 2013 topologies that support mobility.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c42d4-107">I servizi per dispositivi mobili sono disponibili anche nelle distribuzioni ibride.</span><span class="sxs-lookup"><span data-stu-id="c42d4-107">Mobility services are also available in hybrid deployments.</span></span> <span data-ttu-id="c42d4-108">Non è necessario distribuire servizi per supportare i dispositivi mobili se gli utenti si trovano online.</span><span class="sxs-lookup"><span data-stu-id="c42d4-108">You are not required to deploy services for supporting mobility if your users are homed online.</span></span> <span data-ttu-id="c42d4-109">È necessario definire un'impostazione per il servizio di individuazione automatica per consentire agli utenti di dispositivi mobili di trovare la propria identità online.</span><span class="sxs-lookup"><span data-stu-id="c42d4-109">You do need to define a setting for the Autodiscover Service to enable mobile users to find their online identity.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c42d4-110">Se si sta pianificando la connettività degli utenti esterni (ad esempio, Federazione, accesso utente esterno o funzionalità per dispositivi mobili), è necessario utilizzare server perimetrali con il server Standard Edition e il front end server o il pool Front end.</span><span class="sxs-lookup"><span data-stu-id="c42d4-110">If you are planning any external user connectivity (for example, federation, external user access, or mobility features), you must use Edge Servers with Standard Edition server and the Front End Server or Front End pool.</span></span> <span data-ttu-id="c42d4-111">Il server Standard Edition e il front end server o il pool Front end non dispongono dei componenti necessari per consentire agli utenti esterni di accedere alla distribuzione interna o per la distribuzione interna per comunicare con gli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="c42d4-111">The Standard Edition server and the Front End Server or Front End pool do not have the necessary components to enable external users to access your internal deployment, or for the internal deployment to communicate with your external users.</span></span> <span data-ttu-id="c42d4-112">Per tutti gli scenari che includono utenti esterni che collaborano o comunicano con utenti interni, tra cui la mobilità, è necessario distribuire almeno un server perimetrale e un proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="c42d4-112">For all scenarios that include external users collaborating or communicating with internal users, including mobility, you must deploy at least one Edge Server and one reverse proxy.</span></span><BR><span data-ttu-id="c42d4-113"><EM>Notifica push</EM> utilizza un tipo di federazione per i servizi Lync Online, che ospita la casa di compensazione notifiche push (centro PNCH).</span><span class="sxs-lookup"><span data-stu-id="c42d4-113"><EM>Push notification</EM> uses a type of federation to the Lync Online services, which hosts the Push Notification Clearing House (PNCH).</span></span> <span data-ttu-id="c42d4-114">La notifica push si riferisce agli avvisi audio, agli avvisi su schermo (testo) e ai badge che vengono inseriti dalle applicazioni su Apple iPhone, iPad e Windows Phone, quando il dispositivo mobile è inattivo.</span><span class="sxs-lookup"><span data-stu-id="c42d4-114">Push notification refers to the sound alerts, on-screen alerts (text), and badges that are pushed by applications to the Apple iPhone, iPad, and Windows Phone, when the mobile device is inactive.</span></span> <span data-ttu-id="c42d4-115">CENTRO PNCH riceve notifiche push da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c42d4-115">PNCH receives push notifications from Lync Server.</span></span> <span data-ttu-id="c42d4-116">Quando centro PNCH riceve una notifica di un messaggio, centro PNCH inoltra una notifica ai client mobili tramite Apple Push Notification Services o Lync Server 2013 Push Notification Service, in base al client per dispositivi mobili a cui è destinato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="c42d4-116">When PNCH receives a notification of a message, PNCH forwards a notification to mobile clients through either the Apple Push Notification Services or Lync Server 2013 Push Notification Service, based on the mobile client that the message is intended for.</span></span> <span data-ttu-id="c42d4-117">PNCH è un servizio necessario per questi client mobili.</span><span class="sxs-lookup"><span data-stu-id="c42d4-117">PNCH is a required service for these mobile clients.</span></span> <span data-ttu-id="c42d4-118">Per la Federazione di Lync Online, centro PNCH utilizza i server perimetrali e i certificati per garantire la riservatezza e l'autenticazione, i criteri e i record DNS (Domain Name System) correttamente configurati.</span><span class="sxs-lookup"><span data-stu-id="c42d4-118">To federate to Lync Online, PNCH uses Edge Servers and certificates to ensure confidentiality and authentication, policies, and correctly configured domain name system (DNS) records.</span></span> <span data-ttu-id="c42d4-119">I client Nokia Symbian e Android basati su Lync non utilizzano centro PNCH.</span><span class="sxs-lookup"><span data-stu-id="c42d4-119">Nokia Symbian and Android-based Lync Mobile clients do not use PNCH.</span></span> <span data-ttu-id="c42d4-120">Per informazioni dettagliate sulla pianificazione e la distribuzione di server perimetrali, vedere <A href="lync-server-2013-planning-for-external-user-access.md">Planning for External User Access in Lync server 2013</A> e <A href="lync-server-2013-deploying-external-user-access.md">Deploying External User Access in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c42d4-120">For details about planning and deploying Edge Servers, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A> and <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="c42d4-121">I client Lync 2013 mobile per i dispositivi Apple introdotti con gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 non utilizzano più la notifica push o la barra di compensazione notifiche push (centro PNCH).</span><span class="sxs-lookup"><span data-stu-id="c42d4-121">The Lync 2013 Mobile clients for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer use push notification or the push notification clearing house (PNCH).</span></span> <span data-ttu-id="c42d4-122">I client Lync 2013 per dispositivi mobili su Windows Phone utilizzano ancora notifiche push e (centro PNCH).</span><span class="sxs-lookup"><span data-stu-id="c42d4-122">Lync 2013 Mobile clients on Windows Phone still use push notification and the (PNCH).</span></span>



</div>

<div>

## <a name="mobility-components"></a><span data-ttu-id="c42d4-123">Componenti di mobilità</span><span class="sxs-lookup"><span data-stu-id="c42d4-123">Mobility Components</span></span>

<span data-ttu-id="c42d4-124">I servizi che supportano i dispositivi mobili sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="c42d4-124">The services that support mobility are as follows:</span></span>

  - <span data-ttu-id="c42d4-125">**Lync Server 2013 Unified Communications Web API (UCWA)**   fornisce servizi per le comunicazioni in tempo reale con i client mobili e Web in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c42d4-125">**Lync Server 2013 Unified Communications Web API (UCWA)**   Provides services for real-time communications with mobile and web clients in Lync Server 2013.</span></span> <span data-ttu-id="c42d4-126">Quando si distribuiscono gli aggiornamenti cumulativi per Lync Server 2013: February 2013 to the front end server e Director, l'installazione crea una directory virtuale nei servizi Web interni ed esterni (UCWA).</span><span class="sxs-lookup"><span data-stu-id="c42d4-126">When you deploy the Cumulative Updates for Lync Server 2013: February 2013 to the Front End Server and Director, the installation creates a virtual directory in the internal and external web services (Ucwa).</span></span> <span data-ttu-id="c42d4-127">Un componente Web che fa parte della directory virtuale di UCWA accetta le chiamate provenienti da client abilitati a UCWA.</span><span class="sxs-lookup"><span data-stu-id="c42d4-127">A web component that is part of the Ucwa virtual directory accepts calls from UCWA-enabled clients.</span></span> <span data-ttu-id="c42d4-128">Le app client comunicano su un'interfaccia REST per presenza, contatti, messaggistica istantanea, VoIP, video conferenza e collaborazione.</span><span class="sxs-lookup"><span data-stu-id="c42d4-128">The client apps communicate over a REST interface for presence, contacts, instant messaging, VoIP, video conferencing, and collaboration.</span></span> <span data-ttu-id="c42d4-129">UCWA utilizza un canale basato su P-GET per inviare eventi, ad esempio una chiamata in arrivo, un messaggio istantaneo in arrivo o un messaggio all'app client.</span><span class="sxs-lookup"><span data-stu-id="c42d4-129">UCWA uses a P-GET based channel to send events, such as an incoming call, incoming instant message, or a message to the client app.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c42d4-130"><EM>Rest</EM> or Representational State Transfer, è uno stile di architettura software per sistemi distribuiti ampiamente adottati in molte forme ed è adatto ai requisiti dei servizi Web in generale.</span><span class="sxs-lookup"><span data-stu-id="c42d4-130"><EM>REST</EM> or representational state transfer, is a software architectural style for distributed systems that has been widely adopted in many forms and is well suited to the requirements of Web services in general.</span></span>

    
    </div>

  - <span data-ttu-id="c42d4-131">**Lync Server 2013 Mobility Service (MCX)**   questo servizio supporta le funzionalità di Lync, quali messaggistica istantanea, presenza e contatti, su dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="c42d4-131">**Lync Server 2013 Mobility Service (Mcx)**   This service supports Lync functionality, such as instant messaging (IM), presence, and contacts, on mobile devices.</span></span> <span data-ttu-id="c42d4-132">Il servizio per dispositivi mobili è installato in tutti i front end server in ogni pool che supporta la funzionalità di Lync su un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="c42d4-132">The Mobility Service is installed on every Front End Server in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="c42d4-133">Quando si installa Lync Server 2013, viene creata una nuova directory virtuale (MCX) sia nel sito Web interno che nel sito Web esterno nei server front end.</span><span class="sxs-lookup"><span data-stu-id="c42d4-133">When you install Lync Server 2013, a new virtual directory (Mcx) is created under both the internal website and the external website on your Front End Servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c42d4-134">Lync Server 2013 con gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 supporta sia il servizio per dispositivi mobili introdotto nell'aggiornamento cumulativo per Lync Server 2010: novembre 2011, comunemente noto come MCX, sia il componente Web UCWA.</span><span class="sxs-lookup"><span data-stu-id="c42d4-134">Lync Server 2013 with the Cumulative Updates for Lync Server 2013: February 2013 supports both the Mobility service introduced in the Cumulative Update for Lync Server 2010: November 2011, commonly known as Mcx, and the UCWA web component.</span></span> <span data-ttu-id="c42d4-135">La combinazione di questi due servizi per dispositivi mobili fornisce l'interoperabilità e l'utilizzo da parte degli utenti con Lync 2010 mobile e i client mobili Lync 2013 su Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c42d4-135">The combination of these two mobility services provides interoperability and use by users with Lync 2010 Mobile and Lync 2013 Mobile clients on Lync Server 2013.</span></span>

    
    </div>

  - <span data-ttu-id="c42d4-136">**Servizio di individuazione automatica di Lync Server 2013**   questo servizio identifica la posizione dell'utente e consente ai dispositivi mobili e ad altri client Lync di individuare risorse, ad esempio gli URL interni ed esterni per i servizi Web di Lync Server 2013 e l'URL per MCX o UCWA, indipendentemente dal percorso di rete.</span><span class="sxs-lookup"><span data-stu-id="c42d4-136">**Lync Server 2013 Autodiscover Service**   This service identifies the location of the user and enables mobile devices and other Lync clients to locate resources—such as the internal and external URLs for Lync Server 2013 Web Services, and the URL for the Mcx or UCWA—regardless of network location.</span></span> <span data-ttu-id="c42d4-137">Individuazione automatica utilizza nomi host hardcoded (lyncdiscoverinternal per gli utenti all'interno della rete; lyncdiscover per gli utenti all'esterno della rete) e il dominio SIP dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c42d4-137">Automatic discovery uses hardcoded host names (lyncdiscoverinternal for users inside the network; lyncdiscover for users outside the network) and the SIP domain of the user.</span></span> <span data-ttu-id="c42d4-138">Supporta le connessioni client che utilizzano HTTP o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c42d4-138">It supports client connections that use either HTTP or HTTPS.</span></span>
    
    <span data-ttu-id="c42d4-139">Il servizio di individuazione automatica viene installato in tutti i Front End Server e in tutti i Director di ogni pool che supporta le funzionalità di Lync nei dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="c42d4-139">The Autodiscover Service is installed on every Front End Server and on every Director in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="c42d4-140">Quando si installa il servizio di individuazione automatica, viene creata una nuova directory virtuale (individuazione automatica) sia nel sito Web interno che nel sito Web esterno, sia nei front end server che nei direttori.</span><span class="sxs-lookup"><span data-stu-id="c42d4-140">When you install the Autodiscover Service, a new virtual directory (Autodiscover) is created under both the internal website and the external website, on both Front End Servers and Directors.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c42d4-141">Il servizio di individuazione automatica è elencato in questo articolo perché rimane un componente critico quando fornisce servizi client per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="c42d4-141">The Autodiscover Service is listed here because it remains a critical component when providing mobile client services.</span></span> <span data-ttu-id="c42d4-142">Il ruolo dell'individuazione automatica in Lync Server 2013 è stato esteso in modo da fornire servizi per tutti i client.</span><span class="sxs-lookup"><span data-stu-id="c42d4-142">The role of Autodiscover in Lync Server 2013 has been expanded to provide services for all clients.</span></span> <span data-ttu-id="c42d4-143">Per informazioni dettagliate sulla pianificazione del servizio di individuazione automatica, vedere <A href="lync-server-2013-planning-for-autodiscover.md">Planning for Autodiscover in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c42d4-143">For details about planning for the Autodiscover Service, see <A href="lync-server-2013-planning-for-autodiscover.md">Planning for Autodiscover in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="c42d4-144">**Servizio di notifica push**   questo servizio è un servizio basato sul cloud che si trova nel Data Center di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="c42d4-144">**Push Notification Service**   This service is a cloud-based service that is located in the Lync Online data center.</span></span> <span data-ttu-id="c42d4-145">Quando l'applicazione Lync Mobile su un dispositivo Apple iOS supportato o Windows Phone è inattiva, non è in grado di rispondere a nuovi eventi, ad esempio un nuovo invito di messaggistica istantanea, un messaggio istantaneo mancante, una chiamata senza risposta o una segreteria telefonica, perché questi dispositivi non supportano applicazioni mobili in esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="c42d4-145">When the Lync mobile application on a supported Apple iOS device or Windows Phone is inactive, it cannot respond to new events, such as a new instant messaging (IM) invitation, a missed instant message, a missed call, or voice mail, because these devices do not support mobile applications running in the background.</span></span> <span data-ttu-id="c42d4-146">In questi casi, una notifica del nuovo evento, denominata *notifica push*, viene inviata al dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="c42d4-146">In these cases, a notification of the new event—called a *push notification*—is sent to the mobile device.</span></span> <span data-ttu-id="c42d4-147">Il servizio per dispositivi mobili Invia la notifica al servizio di notifica push basato sul cloud, che invia la notifica al servizio notifiche push di Apple (APNS) (per gli strumenti Apple iOS supportati) o al servizio di notifica push di Microsoft (MPNS ) (per Windows Phone), che viene quindi inviato al dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="c42d4-147">The Mobility Service sends the notification to the cloud-based Push Notification Service, which then sends the notification either to the Apple Push Notification Service (APNS) (for supported Apple iOS devices) or to the Microsoft Push Notification Service (MPNS) (for Windows Phone), which then sends it on to the mobile device.</span></span> <span data-ttu-id="c42d4-148">L'utente può quindi rispondere alla notifica sul dispositivo mobile per attivare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c42d4-148">The user can then respond to the notification on the mobile device to activate the application.</span></span>
    
    <span data-ttu-id="c42d4-149">I dispositivi Lync 2010 Mobile su Apple e Windows Phone utilizzano le notifiche push.</span><span class="sxs-lookup"><span data-stu-id="c42d4-149">The Lync 2010 Mobile on Apple and Windows Phone devices use push notifications.</span></span> <span data-ttu-id="c42d4-150">Il client Lync 2013 mobile per i dispositivi Apple introdotti con gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 non utilizza più la notifica push o la barra di compensazione notifiche push (centro PNCH).</span><span class="sxs-lookup"><span data-stu-id="c42d4-150">The Lync 2013 Mobile client for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer uses push notification or the push notification clearing house (PNCH).</span></span>

<span data-ttu-id="c42d4-151">Nel diagramma seguente viene illustrato il modo in cui il servizio di notifica push rientra in una topologia di Lync Server 2013 che utilizza i client mobili di UCWA e Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c42d4-151">The following diagram illustrates how the Push Notification Service fits within a Lync Server 2013 topology that uses UCWA and Lync 2013 Mobile clients.</span></span>

<span data-ttu-id="c42d4-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span><span class="sxs-lookup"><span data-stu-id="c42d4-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span></span>

<span data-ttu-id="c42d4-153">Introdotta in aggiornamento cumulativo per Lync Server 2010: novembre 2011, il servizio MCX fornisce servizi ai client mobili Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="c42d4-153">Introduced in Cumulative Update for Lync Server 2010: November 2011, the Mcx service provides services to Lync 2010 Mobile clients.</span></span> <span data-ttu-id="c42d4-154">Nel diagramma seguente viene illustrato il servizio di notifica push applicato a una topologia utilizzando MCX e i client mobili Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="c42d4-154">The following diagram illustrates the Push Notification Service as it applies to a topology using Mcx and Lync 2010 Mobile clients.</span></span>

<span data-ttu-id="c42d4-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span><span class="sxs-lookup"><span data-stu-id="c42d4-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="c42d4-156">Topologie supportate</span><span class="sxs-lookup"><span data-stu-id="c42d4-156">Supported Topologies</span></span>

<span data-ttu-id="c42d4-157">Applicazione degli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 aggiunge i componenti Web di UCWA per supportare la mobilità per le funzionalità dei client mobili di Lync 2013 nelle topologie seguenti:</span><span class="sxs-lookup"><span data-stu-id="c42d4-157">Applying the Cumulative Updates for Lync Server 2013: February 2013 adds the UCWA web components to support mobility for Lync 2013 Mobile client features in the following topologies:</span></span>

  - <span data-ttu-id="c42d4-158">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="c42d4-158">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="c42d4-159">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="c42d4-159">Lync Server 2013 Enterprise Edition</span></span>

<span data-ttu-id="c42d4-160">Il server perimetrale può essere un server perimetrale di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c42d4-160">The Edge Server can be a Lync Server 2010 Edge Server.</span></span>

<span data-ttu-id="c42d4-161">Una distribuzione di Lync Server 2013 senza gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 utilizzerà il servizio per dispositivi mobili di MCX e potrà fornire servizi solo per Lync 2010 mobile.</span><span class="sxs-lookup"><span data-stu-id="c42d4-161">A Lync Server 2013 deployment without the Cumulative Updates for Lync Server 2013: February 2013 will use the Mcx Mobility Service and can provide services only for Lync 2010 Mobile.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c42d4-162">Il servizio per dispositivi mobili è supportato nei front end server collocati con il ruolo Mediation Server con due interfacce di rete, ma è necessario eseguire le procedure appropriate per configurare le interfacce.</span><span class="sxs-lookup"><span data-stu-id="c42d4-162">The Mobility Service is supported on Front End Servers that is collocated with the Mediation Server role with two network interfaces, but you must take appropriate steps to configure the interfaces.</span></span> <span data-ttu-id="c42d4-163">È necessario assegnare gli indirizzi IP all'interfaccia specifica che comunicherà come Mediation Server e l'IP dell'interfaccia di rete che comunicherà come server front-end.</span><span class="sxs-lookup"><span data-stu-id="c42d4-163">You must assign the IP addresses to the specific interface that will communicate as the Mediation Server, and the network interface IP that will communicate as the Front End Server.</span></span> <span data-ttu-id="c42d4-164">È possibile eseguire questa operazione in Generatore di topologie selezionando l'indirizzo IP corretto per ogni servizio, invece di utilizzare l'impostazione predefinita <STRONG>tutti gli indirizzi IP configurati</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c42d4-164">You can do this in Topology Builder by selecting the correct IP address for each service, instead of using the default <STRONG>Use all configured IP addresses</STRONG>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c42d4-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c42d4-165">See Also</span></span>


[<span data-ttu-id="c42d4-166">Pianificazione dell'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42d4-166">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="c42d4-167">Distribuzione dell'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42d4-167">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)  
[<span data-ttu-id="c42d4-168">Pianificazione dell'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c42d4-168">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

