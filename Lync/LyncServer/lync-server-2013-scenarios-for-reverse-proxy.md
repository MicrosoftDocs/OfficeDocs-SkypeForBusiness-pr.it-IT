---
title: 'Lync Server 2013: scenari per il proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82d5874393e69083ee7058e4e737d21a2fe865ad
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="40b1c-102">Scenari per il proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40b1c-102">Scenarios for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40b1c-103">_**Ultimo argomento modificato:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="40b1c-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="40b1c-104">I proxy inversi sono necessari in Lync Server 2013 per fornire l'accesso ai servizi e alle risorse, come gli URL semplici della riunione e delle chiamate in ingresso, la Rubrica, il contenuto delle riunioni, l'espansione della lista di distribuzione, i servizi per dispositivi mobili e altro.</span><span class="sxs-lookup"><span data-stu-id="40b1c-104">Reverse proxies are required in Lync Server 2013 for providing access to services and resources such as the meeting and dial-in Simple URLs, address book, meeting content, distribution list expansion, mobility services, and others.</span></span> <span data-ttu-id="40b1c-105">Lo scenario tipico del proxy inverso in Lync Server 2013 è consentire ai client esterni (ad esempio, client desktop o client di Lync Web App) l'accesso ai servizi Web esterni del server Director o front end.</span><span class="sxs-lookup"><span data-stu-id="40b1c-105">The typical reverse proxy scenario in Lync Server 2013 is to allow external clients (for example, the desktop client or Lync Web App client) access to the Director or Front End Server external Web Services.</span></span>

<span data-ttu-id="40b1c-106">**Proxy inverso e servizi Web esterni**</span><span class="sxs-lookup"><span data-stu-id="40b1c-106">**Reverse proxy and external web services**</span></span>

<span data-ttu-id="40b1c-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="40b1c-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>

<span data-ttu-id="40b1c-108">Durante la fase di pianificazione, è possibile definire i requisiti per il proxy inverso in una distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40b1c-108">During the planning phase, you define the requirements for the reverse proxy in a Lync Server 2013 deployment.</span></span> <span data-ttu-id="40b1c-109">Il proxy inverso consente di accedere alle funzionalità per i client esterni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40b1c-109">The reverse proxy enables access to features for the following external clients:</span></span>

  - <span data-ttu-id="40b1c-110">Client desktop Microsoft Lync 2013</span><span class="sxs-lookup"><span data-stu-id="40b1c-110">Microsoft Lync 2013 desktop client</span></span>

  - <span data-ttu-id="40b1c-111">Microsoft Lync Web App</span><span class="sxs-lookup"><span data-stu-id="40b1c-111">Microsoft Lync Web App</span></span>

  - <span data-ttu-id="40b1c-112">Microsoft Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="40b1c-112">Microsoft Lync Mobile</span></span>

  - <span data-ttu-id="40b1c-113">App Lync Windows Store</span><span class="sxs-lookup"><span data-stu-id="40b1c-113">Lync Windows Store app</span></span>

<span data-ttu-id="40b1c-114">Quando si pianifica la distribuzione di Lync Server 2013, è necessario eseguire il mapping dei requisiti effettivi per Lync Server 2013 alle funzionalità del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="40b1c-114">When planning your Lync Server 2013 deployment, you map the actual requirements for Lync Server 2013 to the reverse proxy features.</span></span>

1.  <span data-ttu-id="40b1c-115">I client esterni si connetteranno al proxy inverso sulla porta TCP 443 e utilizzeranno Secure Socket Layer (SSL) o Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="40b1c-115">External clients will connect to the reverse proxy on port TCP 443 and will use secure socket layer (SSL) or transport layer security (TLS).</span></span> <span data-ttu-id="40b1c-116">I client Microsoft Lync mobile possono connettersi sulla porta TCP 80, ma solo quando eseguono la connessione iniziale ai servizi di individuazione di Lync e l'amministratore ha configurato i record CNAME (o alias) di DNS (Domain Name System) appropriati e accetta che questo la comunicazione non verrà crittografata.</span><span class="sxs-lookup"><span data-stu-id="40b1c-116">Microsoft Lync Mobile clients can connect on port TCP 80, but only when performing the initial connection to the Lync discover services and the administrator has configured the proper domain name system (DNS) CNAME (or alias) records, and accepts that this communication will not be encrypted.</span></span>

2.  <span data-ttu-id="40b1c-117">I servizi Web esterni di Lync Server 2013 (distribuiti nel front end server e/o nel Director) prevedono una connessione da un proxy inverso sulla porta TCP 4443 e si prevede che la connessione sia SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="40b1c-117">Lync Server 2013 external web services (deployed on the Front End Server and/or the Director) expect a connection from a reverse proxy on port TCP 4443, and it expects that the connection will be SSL/TLS.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="40b1c-118">Le porte di attesa predefinite consigliate per i servizi Web esterni sono TCP 8080 per il traffico HTTP e TCP 4443 per il traffico HTTPS.</span><span class="sxs-lookup"><span data-stu-id="40b1c-118">The suggested default listening ports for the external web services are TCP 8080 for HTTP traffic, and TCP 4443 for HTTPS traffic.</span></span> <span data-ttu-id="40b1c-119">Generatore di topologie consente di ignorare le impostazioni predefinite e di definire le proprie porte di attesa per i servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="40b1c-119">Topology Builder provides an opportunity to override the defaults and define your own listening ports for the external web services.</span></span> <span data-ttu-id="40b1c-120">È importante tenere presente che il proxy inverso comunica con i servizi Web esterni e i client esterni comunicano con il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="40b1c-120">It’s important to note that the reverse proxy communicates with the external web services, and the external clients communicate with the reverse proxy.</span></span> <span data-ttu-id="40b1c-121">Il client esterno comunica con il proxy inverso sulla porta TCP 443, ma è possibile ridefinire la porta in cui il proxy inverso comunica con i servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="40b1c-121">The external client communicates with the reverse proxy on port TCP 443, but you can redefine what port the reverse proxy communicates with the external web services on.</span></span> <span data-ttu-id="40b1c-122">Le opzioni in Generatore di topologie per l'override delle porte di attesa predefinite per i servizi Web consentono di risolvere i conflitti delle porte di attesa che possono verificarsi nell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="40b1c-122">The options in Topology Builder to override the default listening ports for the web services allows you to resolve listening port conflicts that may arise in your infrastructure.</span></span>

    
    </div>

3.  <span data-ttu-id="40b1c-123">I servizi Web esterni di Lync Server 2013 prevedono un'intestazione host non modificata dal client per identificare il servizio e la directory del server Web che il client sta tentando di utilizzare.</span><span class="sxs-lookup"><span data-stu-id="40b1c-123">Lync Server 2013 external web services expect an unmodified Host Header from the client to identify what service and web server directory the client is attempting to use.</span></span> <span data-ttu-id="40b1c-124">Le richieste devono essere visualizzate come provenivano dal proxy inverso</span><span class="sxs-lookup"><span data-stu-id="40b1c-124">Requests should appear as if they came from the reverse proxy</span></span>

4.  <span data-ttu-id="40b1c-125">I servizi Web esterni utilizzano directory virtuali (vDir) del server Web definite che forniscono i servizi offerti ai client.</span><span class="sxs-lookup"><span data-stu-id="40b1c-125">The external web services use defined web server virtual directories (vDir) that provide the services offered to clients.</span></span> <span data-ttu-id="40b1c-126">I servizi Web specifici esternamente identificabili sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="40b1c-126">Specific externally identifiable web services are:</span></span>
    
      - <span data-ttu-id="40b1c-127">VDir "Meet" per riunioni di conferenze Web</span><span class="sxs-lookup"><span data-stu-id="40b1c-127">The “Meet” vDir for web conference meetings</span></span>
    
      - <span data-ttu-id="40b1c-128">VDir "dialin" per l'accesso telefonico e le conferenze telefoniche</span><span class="sxs-lookup"><span data-stu-id="40b1c-128">The “Dialin” vDir for phone access and phone conferencing</span></span>
    
      - <span data-ttu-id="40b1c-129">L'vDir "individuazione automatica" per l'app Lync Windows Store, Lync mobile e il client desktop Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="40b1c-129">The “Autodiscover” vDir for Lync Windows Store app, Lync Mobile, and the desktop client Lync 2013.</span></span> <span data-ttu-id="40b1c-130">Il servizio di individuazione automatica in Lync Server 2013 è noto con il nome DNS "Lyncdiscover"</span><span class="sxs-lookup"><span data-stu-id="40b1c-130">Autodiscover in Lync Server 2013 is known by the DNS name “lyncdiscover”</span></span>
    
      - <span data-ttu-id="40b1c-131">I servizi non definiti sono accessibili dal client esterno tramite chiamate dirette ai servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="40b1c-131">Services not defined are accessed by the external client by direct calls to the external web services.</span></span> <span data-ttu-id="40b1c-132">Ad esempio, il gruppo di distribuzione Expansion (DLX) e il servizio Rubrica (ABS) sono accessibili tramite chiamate dirette ai servizi Web esterni e ai vDirs associati.</span><span class="sxs-lookup"><span data-stu-id="40b1c-132">For example, distribution group expansion (DLX) and the address book service (ABS) are accessed by direct calls to the external web services and associated vDirs.</span></span> <span data-ttu-id="40b1c-133">Il client conosce il percorso effettivo di vDir e costruisce un URL (Uniform record Locator) basato su queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="40b1c-133">The client knows the actual path to the vDir and constructs a uniform record locator (URL) based on this information.</span></span> <span data-ttu-id="40b1c-134">Il client accede al servizio Rubrica utilizzando un URL simile a`https://externalweb.contoso.com/abs/handler`</span><span class="sxs-lookup"><span data-stu-id="40b1c-134">The client would access the address book service using a URL similar to `https://externalweb.contoso.com/abs/handler`</span></span>
    
      - <span data-ttu-id="40b1c-135">Il server Office Web Apps quando le conferenze vengono definite e configurate come parte della topologia di Lync Server</span><span class="sxs-lookup"><span data-stu-id="40b1c-135">The Office Web Apps Server when conferencing is defined and configured as part of the Lync Server topology</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="40b1c-136">Il server Office Web Apps è un server di ruoli separato e non è configurato come parte dei servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="40b1c-136">The Office Web Apps Server is a separate role server and is not configured as part of the external web services.</span></span> <span data-ttu-id="40b1c-137">Questo server viene pubblicato separatamente per l'accesso client.</span><span class="sxs-lookup"><span data-stu-id="40b1c-137">This server is separately published for client access.</span></span>

        
        </div>

5.  <span data-ttu-id="40b1c-138">Definire il bridging SSL per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="40b1c-138">Define SSL bridging for each service.</span></span> <span data-ttu-id="40b1c-139">La porta esterna TCP 443 è mappata alla porta dei servizi Web esterni di TCP 4443.</span><span class="sxs-lookup"><span data-stu-id="40b1c-139">The external port TCP 443 is mapped to the external web services port of TCP 4443.</span></span> <span data-ttu-id="40b1c-140">Per HTTP non crittografato, la porta TCP 80 è mappata alla porta dei servizi Web esterni TCP 8080</span><span class="sxs-lookup"><span data-stu-id="40b1c-140">For unencrypted HTTP, port TCP 80 is mapped to the external web services port TCP 8080</span></span>

6.  <span data-ttu-id="40b1c-141">Pianificare la pubblicazione delle risorse del server Web per i listener proxy inversi</span><span class="sxs-lookup"><span data-stu-id="40b1c-141">Plan for reverse proxy listeners to publish web server resources</span></span>

7.  <span data-ttu-id="40b1c-142">Richiedere e configurare il certificato per il proxy inverso in base ai servizi che verranno offerti.</span><span class="sxs-lookup"><span data-stu-id="40b1c-142">Request and configure the certificate for the reverse proxy based on the services that will be offered.</span></span> <span data-ttu-id="40b1c-143">Se configurato con i nomi alternativi del soggetto corretti, questo certificato può essere condiviso da tutti i listener configurati nel server proxy inverso</span><span class="sxs-lookup"><span data-stu-id="40b1c-143">If configured with the correct subject alternative names, this certificate can be shared by all configured listeners on the reverse proxy server</span></span>

<span data-ttu-id="40b1c-144">Risorse disponibili per la pianificazione della distribuzione del proxy inverso:</span><span class="sxs-lookup"><span data-stu-id="40b1c-144">Resources available for planning your reverse proxy deployment:</span></span>

  - [<span data-ttu-id="40b1c-145">Raccolta dati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40b1c-145">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="40b1c-146">Riepilogo del certificato-proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40b1c-146">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="40b1c-147">Riepilogo delle porte-proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40b1c-147">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="40b1c-148">Riepilogo DNS-proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40b1c-148">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

