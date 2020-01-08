---
title: 'Lync Server 2013: Scenari per i proxy inversi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1621e8bb0241e82f9f4678d4fe39a4f66f6bcf9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="2e5f1-102">Scenari per i proxy inversi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e5f1-102">Scenarios for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e5f1-103">_**Argomento Ultima modifica:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="2e5f1-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="2e5f1-104">I proxy inversi sono necessari in Lync Server 2013 per consentire l'accesso a servizi e risorse, come gli URL semplici della riunione e della chiamata in ingresso, la Rubrica, il contenuto della riunione, l'espansione della lista di distribuzione, i servizi di mobilità e altri.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-104">Reverse proxies are required in Lync Server 2013 for providing access to services and resources such as the meeting and dial-in Simple URLs, address book, meeting content, distribution list expansion, mobility services, and others.</span></span> <span data-ttu-id="2e5f1-105">Lo scenario di proxy inverso tipico in Lync Server 2013 consente ai client esterni, ad esempio client desktop o client Lync Web App, di accedere ai servizi Web esterni di Director o front end server.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-105">The typical reverse proxy scenario in Lync Server 2013 is to allow external clients (for example, the desktop client or Lync Web App client) access to the Director or Front End Server external Web Services.</span></span>

<span data-ttu-id="2e5f1-106">**Proxy inverso e servizi Web esterni**</span><span class="sxs-lookup"><span data-stu-id="2e5f1-106">**Reverse proxy and external web services**</span></span>

<span data-ttu-id="2e5f1-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9") -45b7-a8b7-a8c89f09c97c</span><span class="sxs-lookup"><span data-stu-id="2e5f1-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>

<span data-ttu-id="2e5f1-108">Durante la fase di pianificazione, è possibile definire i requisiti per il proxy inverso in una distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-108">During the planning phase, you define the requirements for the reverse proxy in a Lync Server 2013 deployment.</span></span> <span data-ttu-id="2e5f1-109">Il proxy inverso consente l'accesso alle funzionalità per i client esterni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2e5f1-109">The reverse proxy enables access to features for the following external clients:</span></span>

  - <span data-ttu-id="2e5f1-110">Client desktop di Microsoft Lync 2013</span><span class="sxs-lookup"><span data-stu-id="2e5f1-110">Microsoft Lync 2013 desktop client</span></span>

  - <span data-ttu-id="2e5f1-111">Microsoft Lync Web App</span><span class="sxs-lookup"><span data-stu-id="2e5f1-111">Microsoft Lync Web App</span></span>

  - <span data-ttu-id="2e5f1-112">Microsoft Lync mobile</span><span class="sxs-lookup"><span data-stu-id="2e5f1-112">Microsoft Lync Mobile</span></span>

  - <span data-ttu-id="2e5f1-113">App Lync di Windows Store</span><span class="sxs-lookup"><span data-stu-id="2e5f1-113">Lync Windows Store app</span></span>

<span data-ttu-id="2e5f1-114">Quando si pianifica la distribuzione di Lync Server 2013, è possibile eseguire il mapping dei requisiti effettivi per Lync Server 2013 alle funzionalità proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-114">When planning your Lync Server 2013 deployment, you map the actual requirements for Lync Server 2013 to the reverse proxy features.</span></span>

1.  <span data-ttu-id="2e5f1-115">I client esterni si connetteranno al proxy inverso sulla porta TCP 443 e useranno Secure Socket Layer (SSL) o Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="2e5f1-115">External clients will connect to the reverse proxy on port TCP 443 and will use secure socket layer (SSL) or transport layer security (TLS).</span></span> <span data-ttu-id="2e5f1-116">I client di Microsoft Lync mobile possono connettersi alla porta TCP 80, ma solo quando si esegue la connessione iniziale ai servizi di individuazione Lync e l'amministratore ha configurato i record CNAME (o alias) DNS (Domain Name System) appropriati e accetta che questo le comunicazioni non verranno crittografate.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-116">Microsoft Lync Mobile clients can connect on port TCP 80, but only when performing the initial connection to the Lync discover services and the administrator has configured the proper domain name system (DNS) CNAME (or alias) records, and accepts that this communication will not be encrypted.</span></span>

2.  <span data-ttu-id="2e5f1-117">I servizi Web esterni di Lync Server 2013 (distribuiti nel server front-end e/o nel Director) prevedono una connessione da un proxy inverso sulla porta TCP 4443 e prevede che la connessione sarà SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-117">Lync Server 2013 external web services (deployed on the Front End Server and/or the Director) expect a connection from a reverse proxy on port TCP 4443, and it expects that the connection will be SSL/TLS.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2e5f1-118">Le porte di ascolto predefinite suggerite per i servizi Web esterni sono TCP 8080 per il traffico HTTP e TCP 4443 per il traffico HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-118">The suggested default listening ports for the external web services are TCP 8080 for HTTP traffic, and TCP 4443 for HTTPS traffic.</span></span> <span data-ttu-id="2e5f1-119">Generatore di topologia offre l'opportunità di ignorare le impostazioni predefinite e definire le proprie porte di ascolto per i servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-119">Topology Builder provides an opportunity to override the defaults and define your own listening ports for the external web services.</span></span> <span data-ttu-id="2e5f1-120">È importante notare che il proxy inverso comunica con i servizi Web esterni e i client esterni comunicano con il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-120">It’s important to note that the reverse proxy communicates with the external web services, and the external clients communicate with the reverse proxy.</span></span> <span data-ttu-id="2e5f1-121">Il client esterno comunica con il proxy inverso sulla porta TCP 443, ma è possibile ridefinire la porta con cui il proxy inverso comunica con i servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-121">The external client communicates with the reverse proxy on port TCP 443, but you can redefine what port the reverse proxy communicates with the external web services on.</span></span> <span data-ttu-id="2e5f1-122">Le opzioni in Generatore di topologie per ignorare le porte di ascolto predefinite per i servizi Web consentono di risolvere i conflitti di porta di ascolto che potrebbero verificarsi nell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-122">The options in Topology Builder to override the default listening ports for the web services allows you to resolve listening port conflicts that may arise in your infrastructure.</span></span>

    
    </div>

3.  <span data-ttu-id="2e5f1-123">I servizi Web esterni di Lync Server 2013 si aspettano un'intestazione host non modificata dal client per identificare il servizio e la directory del server Web che il client sta provando a usare.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-123">Lync Server 2013 external web services expect an unmodified Host Header from the client to identify what service and web server directory the client is attempting to use.</span></span> <span data-ttu-id="2e5f1-124">Le richieste devono essere visualizzate come provenivano dal proxy inverso</span><span class="sxs-lookup"><span data-stu-id="2e5f1-124">Requests should appear as if they came from the reverse proxy</span></span>

4.  <span data-ttu-id="2e5f1-125">I servizi Web esterni usano le directory virtuali server Web definite (vDir) che offrono i servizi offerti ai client.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-125">The external web services use defined web server virtual directories (vDir) that provide the services offered to clients.</span></span> <span data-ttu-id="2e5f1-126">I servizi Web specifici esternamente identificabili sono:</span><span class="sxs-lookup"><span data-stu-id="2e5f1-126">Specific externally identifiable web services are:</span></span>
    
      - <span data-ttu-id="2e5f1-127">VDir "riunione" per le riunioni di conferenza Web</span><span class="sxs-lookup"><span data-stu-id="2e5f1-127">The “Meet” vDir for web conference meetings</span></span>
    
      - <span data-ttu-id="2e5f1-128">VDir "chiamata" per l'accesso telefonico e le conferenze telefoniche</span><span class="sxs-lookup"><span data-stu-id="2e5f1-128">The “Dialin” vDir for phone access and phone conferencing</span></span>
    
      - <span data-ttu-id="2e5f1-129">Il vDir "individuazione automatica" per l'app Lync di Windows Store, Lync mobile e il client desktop Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-129">The “Autodiscover” vDir for Lync Windows Store app, Lync Mobile, and the desktop client Lync 2013.</span></span> <span data-ttu-id="2e5f1-130">L'individuazione automatica in Lync Server 2013 è nota con il nome DNS "Lyncdiscover"</span><span class="sxs-lookup"><span data-stu-id="2e5f1-130">Autodiscover in Lync Server 2013 is known by the DNS name “lyncdiscover”</span></span>
    
      - <span data-ttu-id="2e5f1-131">I servizi non definiti sono accessibili dal client esterno tramite chiamate dirette ai servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-131">Services not defined are accessed by the external client by direct calls to the external web services.</span></span> <span data-ttu-id="2e5f1-132">Ad esempio, l'espansione del gruppo di distribuzione (DLX) e il servizio Rubrica (ABS) sono accessibili tramite chiamate dirette ai servizi Web esterni e ai vDirs associati.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-132">For example, distribution group expansion (DLX) and the address book service (ABS) are accessed by direct calls to the external web services and associated vDirs.</span></span> <span data-ttu-id="2e5f1-133">Il client conosce il percorso effettivo di vDir e costruisce un URL (Uniform record Locator) in base a queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-133">The client knows the actual path to the vDir and constructs a uniform record locator (URL) based on this information.</span></span> <span data-ttu-id="2e5f1-134">Il client accede al servizio Rubrica usando un URL simile a`https://externalweb.contoso.com/abs/handler`</span><span class="sxs-lookup"><span data-stu-id="2e5f1-134">The client would access the address book service using a URL similar to `https://externalweb.contoso.com/abs/handler`</span></span>
    
      - <span data-ttu-id="2e5f1-135">Il server Office Web Apps quando la conferenza viene definita e configurata come parte della topologia di Lync Server</span><span class="sxs-lookup"><span data-stu-id="2e5f1-135">The Office Web Apps Server when conferencing is defined and configured as part of the Lync Server topology</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2e5f1-136">Il server Office Web Apps è un server di ruoli distinto e non è configurato come parte dei servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-136">The Office Web Apps Server is a separate role server and is not configured as part of the external web services.</span></span> <span data-ttu-id="2e5f1-137">Questo server viene pubblicato separatamente per l'accesso client.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-137">This server is separately published for client access.</span></span>

        
        </div>

5.  <span data-ttu-id="2e5f1-138">Definire il bridging SSL per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-138">Define SSL bridging for each service.</span></span> <span data-ttu-id="2e5f1-139">La porta esterna TCP 443 viene mappata alla porta dei servizi Web esterni di TCP 4443.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-139">The external port TCP 443 is mapped to the external web services port of TCP 4443.</span></span> <span data-ttu-id="2e5f1-140">Per HTTP non crittografato, la porta TCP 80 viene mappata alla porta dei servizi Web esterni TCP 8080</span><span class="sxs-lookup"><span data-stu-id="2e5f1-140">For unencrypted HTTP, port TCP 80 is mapped to the external web services port TCP 8080</span></span>

6.  <span data-ttu-id="2e5f1-141">Pianificare l'inversione dei listener proxy per pubblicare le risorse del server Web</span><span class="sxs-lookup"><span data-stu-id="2e5f1-141">Plan for reverse proxy listeners to publish web server resources</span></span>

7.  <span data-ttu-id="2e5f1-142">Richiedere e configurare il certificato per il proxy inverso in base ai servizi che verranno offerti.</span><span class="sxs-lookup"><span data-stu-id="2e5f1-142">Request and configure the certificate for the reverse proxy based on the services that will be offered.</span></span> <span data-ttu-id="2e5f1-143">Se configurato con i nomi alternativi del soggetto corretti, questo certificato può essere condiviso da tutti i listener configurati nel server proxy inverso</span><span class="sxs-lookup"><span data-stu-id="2e5f1-143">If configured with the correct subject alternative names, this certificate can be shared by all configured listeners on the reverse proxy server</span></span>

<span data-ttu-id="2e5f1-144">Risorse disponibili per pianificare la distribuzione del proxy inverso:</span><span class="sxs-lookup"><span data-stu-id="2e5f1-144">Resources available for planning your reverse proxy deployment:</span></span>

  - [<span data-ttu-id="2e5f1-145">Raccolta dati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e5f1-145">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="2e5f1-146">Riepilogo dei certificati - proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e5f1-146">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="2e5f1-147">Riepilogo delle porte - proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e5f1-147">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="2e5f1-148">Riepilogo di DNS - proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e5f1-148">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

