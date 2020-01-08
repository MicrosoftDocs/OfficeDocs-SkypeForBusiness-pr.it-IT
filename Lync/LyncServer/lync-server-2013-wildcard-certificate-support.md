---
title: 'Lync Server 2013: Supporto dei certificati con caratteri jolly'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9422c3bebbb5fb32be88cfe5c41968207bbed2ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a><span data-ttu-id="40790-102">Supporto dei certificati con caratteri jolly in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40790-102">Wildcard certificate support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40790-103">_**Argomento Ultima modifica:** 2013-03-21_</span><span class="sxs-lookup"><span data-stu-id="40790-103">_**Topic Last Modified:** 2013-03-21_</span></span>

<span data-ttu-id="40790-104">Lync Server 2013 USA i certificati per consentire l'autenticazione delle comunicazioni e delle identità del server.</span><span class="sxs-lookup"><span data-stu-id="40790-104">Lync Server 2013 uses certificates to provide communications encryption and server identity authentication.</span></span> <span data-ttu-id="40790-105">In alcuni casi, ad esempio la pubblicazione Web tramite il proxy inverso, il nome di voce alternativo soggetto forte (SAN) corrispondente al nome di dominio completo (FQDN) del server che presenta il servizio non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="40790-105">In some cases, such as web publishing through the reverse proxy, strong subject alternative name (SAN) entry matching to the fully qualified domain name (FQDN) of the server presenting the service is not required.</span></span> <span data-ttu-id="40790-106">In questi casi, è possibile usare i certificati con le voci SAN jolly (comunemente note come "certificati con caratteri jolly") per ridurre il costo di un certificato richiesto da un'autorità di certificazione pubblica e ridurre la complessità del processo di pianificazione per i certificati .</span><span class="sxs-lookup"><span data-stu-id="40790-106">In these cases, you can use certificates with wildcard SAN entries (commonly known as “wildcard certificates”) to reduce the cost of a certificate requested from a public certification authority and to reduce the complexity of the planning process for certificates.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="40790-107">Per mantenere la funzionalità dei dispositivi UC (Unified Communications), ad esempio i telefoni da tavolo, è consigliabile testare attentamente il certificato distribuito per verificare che i dispositivi funzionino correttamente dopo l'implementazione di un certificato con caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="40790-107">To retain the functionality of unified communications (UC) devices (for example, desk phones), you should test the deployed certificate carefully to ensure that devices function properly after you implement a wildcard certificate.</span></span>



</div>

<span data-ttu-id="40790-108">Per qualsiasi ruolo non è disponibile alcun supporto per una voce con carattere jolly come nome dell'oggetto, denominato anche nome comune o CN.</span><span class="sxs-lookup"><span data-stu-id="40790-108">There is no support for a wildcard entry as the subject name (also referred to as the common name or CN) for any role.</span></span> <span data-ttu-id="40790-109">I ruoli del server seguenti sono supportati quando si usano voci con caratteri jolly nella SAN:</span><span class="sxs-lookup"><span data-stu-id="40790-109">The following server roles are supported when using wildcard entries in the SAN:</span></span>

  - <span></span>  
    <span data-ttu-id="40790-110">**Proxy inverso.**    La voce San jolly è supportata per il certificato di pubblicazione URL semplice (riunione e chiamata).</span><span class="sxs-lookup"><span data-stu-id="40790-110">**Reverse proxy.**   Wildcard SAN entry is supported for Simple URL (meet and dialin) publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="40790-111">**Proxy inverso.**    La voce San jolly è supportata per le voci San per Lyncdiscover nel certificato di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="40790-111">**Reverse proxy.**   Wildcard SAN entry is supported for the SAN entries for LyncDiscover on the publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="40790-112">**Director.**    La voce San jolly è supportata per gli URL semplici (riunione e chiamata) e per le voci San per Lyncdiscover e lyncdiscoverinternal in Director Web Components.</span><span class="sxs-lookup"><span data-stu-id="40790-112">**Director.**   Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Director web components.</span></span>

  - <span></span>  
    <span data-ttu-id="40790-113">**Server front-end (Standard Edition) e pool Front-End (Enterprise Edition).**</span><span class="sxs-lookup"><span data-stu-id="40790-113">**Front End Server (Standard Edition) and Front End pool (Enterprise Edition).**</span></span> <span data-ttu-id="40790-114">La voce SAN jolly è supportata per gli URL semplici (riunione e chiamata) e per le voci SAN per LyncDiscover e LyncDiscoverInternal nei componenti Web front-end.</span><span class="sxs-lookup"><span data-stu-id="40790-114">Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Front End web components.</span></span>

  - <span></span>  
    <span data-ttu-id="40790-115">**Messaggistica unificata di Exchange (UM).**    Il server non usa le voci San quando viene distribuito come server autonomo.</span><span class="sxs-lookup"><span data-stu-id="40790-115">**Exchange Unified Messaging (UM).**   The server does not use SAN entries when deployed as a stand-alone server.</span></span>

  - <span></span>  
    <span data-ttu-id="40790-116">**Server Accesso client di Microsoft Exchange Server.**    Le voci con caratteri jolly nella San sono supportate per i client interni ed esterni.</span><span class="sxs-lookup"><span data-stu-id="40790-116">**Microsoft Exchange Server Client Access server.**   Wildcard entries in the SAN are supported for internal and external clients.</span></span>

  - <span></span>  
    <span data-ttu-id="40790-117">**Messaggistica UNIFICAta di Exchange e server Accesso client di Microsoft Exchange Server nello stesso server.**    Sono supportate le voci San con caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="40790-117">**Exchange Unified Messaging (UM) and Microsoft Exchange Server Client Access server on same server.**   Wildcard SAN entries are supported.</span></span>

<span data-ttu-id="40790-118">Ruoli del server non trattati in questo argomento:</span><span class="sxs-lookup"><span data-stu-id="40790-118">Server roles that are not addressed in this topic:</span></span>

  - <span data-ttu-id="40790-119">Ruoli del server interni (inclusi, ma non limitati a Mediation Server, server di archiviazione e monitoraggio, Survivable Branch Appliance o Survivable Branch Server)</span><span class="sxs-lookup"><span data-stu-id="40790-119">Internal server roles (including, but not limited to the Mediation Server, Archiving and Monitoring Server, Survivable Branch Appliance, or Survivable Branch Server)</span></span>

  - <span data-ttu-id="40790-120">Interfacce di Edge Server esterne</span><span class="sxs-lookup"><span data-stu-id="40790-120">External Edge Server interfaces</span></span>

  - <span data-ttu-id="40790-121">Server perimetrale interno</span><span class="sxs-lookup"><span data-stu-id="40790-121">Internal Edge Server</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="40790-122">Per l'interfaccia Internal Edge Server, è possibile assegnare una voce con carattere jolly alla SAN ed è supportata.</span><span class="sxs-lookup"><span data-stu-id="40790-122">For the internal Edge Server interface, a wildcard entry can be assigned to the SAN, and is supported.</span></span> <span data-ttu-id="40790-123">La SAN nel server perimetrale interno non viene eseguita una query e una voce SAN con carattere jolly è di valore limitato.</span><span class="sxs-lookup"><span data-stu-id="40790-123">The SAN on the internal Edge Server is not queried, and a wildcard SAN entry is of limited value.</span></span>

    
    </div>

<span data-ttu-id="40790-124">Per informazioni dettagliate sulle configurazioni dei certificati, incluso l'uso di caratteri jolly nei certificati, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="40790-124">For details about certificate configurations, including the use of wildcards in certificates, see the following topics:</span></span>

  - [<span data-ttu-id="40790-125">Requisiti dei certificati per i server interni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40790-125">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="40790-126">Requisiti dei certificati per l'accesso utente esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40790-126">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="40790-127">Riepilogo dei certificati - bilanciamento del carico DNS e bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40790-127">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="40790-128">Riepilogo dei certificati - singolo server Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40790-128">Certificate summary - Single Director in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-director.md)

  - [<span data-ttu-id="40790-129">Riepilogo dei certificati - pool di server Director con scalabilità implementata, servizio di bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40790-129">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="40790-130">Riepilogo dei certificati - proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40790-130">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="40790-131">Linee guida per l'integrazione della messaggistica unificata locale con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40790-131">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

<span data-ttu-id="40790-132">Per informazioni dettagliate sulla configurazione dei certificati per Exchange, incluso l'uso di caratteri jolly, vedere la documentazione del prodotto Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="40790-132">For details about configuring certificates for Exchange, including the use of wildcards, see the Exchange 2013 product documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

