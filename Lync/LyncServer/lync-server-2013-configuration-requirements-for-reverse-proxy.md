---
title: 'Lync Server 2013: requisiti di configurazione per il proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b19684913f147eed353ff9f69400e9993de40c12
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="48f94-102">Requisiti di configurazione per il proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48f94-102">Configuration requirements for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48f94-103">_**Ultimo argomento modificato:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="48f94-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="48f94-104">Lync Server 2013 impone alcuni requisiti per le comunicazioni provenienti dal client esterno, che vengono quindi passate ai servizi Web esterni ospitati nel server Director, nel pool di Director, nel front-end o nel pool Front end.</span><span class="sxs-lookup"><span data-stu-id="48f94-104">Lync Server 2013 imposes a few requirements on communications from the external client that are then passed on to the external Web services hosted on the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="48f94-105">Il proxy inverso è anche responsabile della pubblicazione del server Office Web Apps, se si offrono servizi di audioconferenza agli utenti.</span><span class="sxs-lookup"><span data-stu-id="48f94-105">The reverse proxy is also responsible for publishing the Office Web Apps Server, if you are offering conferencing to your users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48f94-106">Lync Server 2013 non specifica un particolare proxy inverso che è necessario utilizzare.</span><span class="sxs-lookup"><span data-stu-id="48f94-106">Lync Server 2013 does not specify a particular reverse proxy that you must use.</span></span> <span data-ttu-id="48f94-107">Lync Server 2013 definisce solo i requisiti operativi che il proxy inverso deve essere in grado di eseguire.</span><span class="sxs-lookup"><span data-stu-id="48f94-107">Lync Server 2013 only defines operational requirements that the reverse proxy must be able to do.</span></span> <span data-ttu-id="48f94-108">In genere, il proxy inverso già distribuito nell'infrastruttura potrebbe essere in grado di soddisfare i requisiti.</span><span class="sxs-lookup"><span data-stu-id="48f94-108">Typically, the reverse proxy that you already have deployed in your infrastructure may be able to meet the requirements.</span></span>



</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="48f94-109">Requisiti relativi al proxy inverso</span><span class="sxs-lookup"><span data-stu-id="48f94-109">Reverse Proxy Requirements</span></span>

<span data-ttu-id="48f94-110">Le operazioni funzionali che Lync Server 2013 prevede che un proxy inverso venga eseguito sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="48f94-110">The functional operations that Lync Server 2013 expect a reverse proxy to perform are:</span></span>

  - <span data-ttu-id="48f94-111">Utilizzare Secure Socket Layer (SSL) e Transport Layer Security (TLS) implementato utilizzando i certificati acquisiti da un'autorità di certificazione pubblica per la connessione ai servizi Web esterni pubblicati del server Director, del pool di Director, del front-end o del pool Front end.</span><span class="sxs-lookup"><span data-stu-id="48f94-111">Use secure socket layer (SSL) and transport layer security (TLS) implemented by using certificates acquired from a public certification authority to connect to the published external Web services of the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="48f94-112">Il server Director e front end può essere in un pool con bilanciamento del carico tramite i dispositivi di compensazione del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="48f94-112">The Director and the Front End Server can be in a load-balanced pool by using hardware load balancers.</span></span>

  - <span data-ttu-id="48f94-113">In grado di pubblicare siti Web interni utilizzando i certificati per la crittografia oppure pubblicarli in modo non crittografato, se necessario.</span><span class="sxs-lookup"><span data-stu-id="48f94-113">Able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>

  - <span data-ttu-id="48f94-114">In grado di pubblicare un sito Web ospitato internamente tramite un nome di dominio completo (FQDN, Fully Qualified Domain Name).</span><span class="sxs-lookup"><span data-stu-id="48f94-114">Able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>

  - <span data-ttu-id="48f94-115">In grado di pubblicare tutto il contenuto del sito Web ospitato.</span><span class="sxs-lookup"><span data-stu-id="48f94-115">Able to publish all contents of the hosted web site.</span></span> <span data-ttu-id="48f94-116">Per impostazione predefinita, è possibile utilizzare \*\* / \*\* la direttiva, riconosciuta dalla maggior parte dei server Web per indicare "pubblicare tutto il contenuto sul server Web".</span><span class="sxs-lookup"><span data-stu-id="48f94-116">By default, you can use the **/\*** directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="48f94-117">È inoltre possibile modificare la direttiva, ad esempio **/Uwca/\***, che significa "pubblicare tutto il contenuto nella directory virtuale UCWA".</span><span class="sxs-lookup"><span data-stu-id="48f94-117">You can also modify the directive—for example, **/Uwca/\***, which means "Publish all content under the virtual directory Ucwa."</span></span>

  - <span data-ttu-id="48f94-118">Deve essere configurabile per richiedere connessioni Secure Sockets Layer (SSL) e/o Transport Layer Security (TLS) con client che richiedono contenuti da un sito Web pubblicato.</span><span class="sxs-lookup"><span data-stu-id="48f94-118">Must be configurable to require Secure Sockets Layer (SSL) and/or Transport Layer Security (TLS) connections with clients that request content from a published website.</span></span>

  - <span data-ttu-id="48f94-119">Deve accettare i certificati con le voci del nome alternativo soggetto (SAN).</span><span class="sxs-lookup"><span data-stu-id="48f94-119">Must accept certificates with subject alternative name (SAN) entries.</span></span>

  - <span data-ttu-id="48f94-120">Deve essere in grado di consentire l'associazione di un certificato a un listener o a un'interfaccia tramite la quale verrà risolto il nome di dominio completo dei servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="48f94-120">Must be able to allow binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="48f94-121">Le configurazioni dei listener sono preferibili alle interfacce.</span><span class="sxs-lookup"><span data-stu-id="48f94-121">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="48f94-122">Molti listener possono essere configurati in una singola interfaccia.</span><span class="sxs-lookup"><span data-stu-id="48f94-122">Many listeners can be configured on a single interface.</span></span>

  - <span data-ttu-id="48f94-123">Deve consentire la configurazione della gestione delle intestazioni host.</span><span class="sxs-lookup"><span data-stu-id="48f94-123">Must allow for the configuration of host header handling.</span></span> <span data-ttu-id="48f94-124">Spesso, l'intestazione host originale inviata dal client richiedente deve essere passata in modo trasparente, anziché essere modificata dal proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="48f94-124">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>

  - <span data-ttu-id="48f94-125">Bridging del traffico SSL e TLS da una porta definita esternamente (ad esempio, TCP 443) a un'altra porta definita (ad esempio, TCP 4443).</span><span class="sxs-lookup"><span data-stu-id="48f94-125">Bridging of SSL and TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="48f94-126">Il proxy inverso può decrittografare il pacchetto al ricevimento e quindi rieseguire la crittografia del pacchetto all'invio.</span><span class="sxs-lookup"><span data-stu-id="48f94-126">The reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>

  - <span data-ttu-id="48f94-127">Bridging del traffico TCP non crittografato da una porta (ad esempio, TCP 80) a un altro (ad esempio, TCP 8080).</span><span class="sxs-lookup"><span data-stu-id="48f94-127">Bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>

  - <span data-ttu-id="48f94-128">Consenti configurazione o accettazione dell'autenticazione NTLM, nessuna autenticazione e autenticazione pass-through.</span><span class="sxs-lookup"><span data-stu-id="48f94-128">Allow configuration of, or accept, NTLM authentication, No authentication and Pass-through authentication.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

