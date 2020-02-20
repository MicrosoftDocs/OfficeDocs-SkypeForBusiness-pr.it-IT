---
title: Supporto per i certificati con caratteri jolly di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d48ba92ffd18e385be95d6218357303a67f892c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a><span data-ttu-id="5098e-102">Supporto per i certificati con caratteri jolly in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5098e-102">Wildcard certificate support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5098e-103">_**Ultimo argomento modificato:** 2013-03-21_</span><span class="sxs-lookup"><span data-stu-id="5098e-103">_**Topic Last Modified:** 2013-03-21_</span></span>

<span data-ttu-id="5098e-104">Lync Server 2013 utilizza i certificati per fornire la crittografia delle comunicazioni e l'autenticazione dell'identità del server.</span><span class="sxs-lookup"><span data-stu-id="5098e-104">Lync Server 2013 uses certificates to provide communications encryption and server identity authentication.</span></span> <span data-ttu-id="5098e-105">In alcuni casi, ad esempio per la pubblicazione Web tramite il proxy inverso, non è necessaria la corrispondenza esatta tra la voce di nome alternativo del soggetto e il nome di dominio completo (FQDN) del server che presenta il servizio.</span><span class="sxs-lookup"><span data-stu-id="5098e-105">In some cases, such as web publishing through the reverse proxy, strong subject alternative name (SAN) entry matching to the fully qualified domain name (FQDN) of the server presenting the service is not required.</span></span> <span data-ttu-id="5098e-106">In questi casi è possibile utilizzare certificati con voci di nome alternativo del soggetto con caratteri jolly, comunemente noti come "certificati con caratteri jolly", per ridurre il costo di un certificato richiesto a un'autorità di certificazione pubblica e per semplificare il processo di pianificazione per i certificati.</span><span class="sxs-lookup"><span data-stu-id="5098e-106">In these cases, you can use certificates with wildcard SAN entries (commonly known as “wildcard certificates”) to reduce the cost of a certificate requested from a public certification authority and to reduce the complexity of the planning process for certificates.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="5098e-107">Per mantenere la funzionalità dei dispositivi per le comunicazioni unificate, quali ad esempio i telefoni da tavolo, è necessario verificare attentamente il certificato distribuito per assicurarsi che i dispositivi funzionino correttamente dopo l'implementazione di un certificato con caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="5098e-107">To retain the functionality of unified communications (UC) devices (for example, desk phones), you should test the deployed certificate carefully to ensure that devices function properly after you implement a wildcard certificate.</span></span>



</div>

<span data-ttu-id="5098e-p102">Non viene fornito il supporto per una voce con caratteri jolly come nome soggetto, ovvero come nome comune o CN, per alcun ruolo. Quando si utilizzano voci con caratteri jolly nel nome alternativo del soggetto, sono supportati i ruoli del server seguenti:</span><span class="sxs-lookup"><span data-stu-id="5098e-p102">There is no support for a wildcard entry as the subject name (also referred to as the common name or CN) for any role. The following server roles are supported when using wildcard entries in the SAN:</span></span>

  - <span></span>  
    <span data-ttu-id="5098e-110">**Proxy inverso.**    La voce San jolly è supportata per il certificato di pubblicazione URL semplice (Meet e dialin).</span><span class="sxs-lookup"><span data-stu-id="5098e-110">**Reverse proxy.**   Wildcard SAN entry is supported for Simple URL (meet and dialin) publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="5098e-111">**Proxy inverso.**    La voce San jolly è supportata per le voci San per Lyncdiscover nel certificato di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5098e-111">**Reverse proxy.**   Wildcard SAN entry is supported for the SAN entries for LyncDiscover on the publishing certificate.</span></span>

  - <span></span>  
    <span data-ttu-id="5098e-112">**Director.**    La voce San jolly è supportata per gli URL semplici (Meet e dialin) e per le voci San per Lyncdiscover e lyncdiscoverinternal in Director Web Components.</span><span class="sxs-lookup"><span data-stu-id="5098e-112">**Director.**   Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Director web components.</span></span>

  - <span></span>  
    <span data-ttu-id="5098e-113">**Front End Server (Standard Edition) e pool Front End (Enterprise Edition).**</span><span class="sxs-lookup"><span data-stu-id="5098e-113">**Front End Server (Standard Edition) and Front End pool (Enterprise Edition).**</span></span> <span data-ttu-id="5098e-114">La voce SAN jolly è supportata per gli URL semplici (Meet e dialin) e per le voci SAN per LyncDiscover e LyncDiscoverInternal nei componenti Web front-end.</span><span class="sxs-lookup"><span data-stu-id="5098e-114">Wildcard SAN entry is supported for Simple URLs (meet and dialin) and for SAN entries for LyncDiscover and LyncDiscoverInternal in Front End web components.</span></span>

  - <span></span>  
    <span data-ttu-id="5098e-115">**Messaggistica unificata di Exchange (UM).**    Il server non utilizza le voci di San quando viene distribuito come server autonomo.</span><span class="sxs-lookup"><span data-stu-id="5098e-115">**Exchange Unified Messaging (UM).**   The server does not use SAN entries when deployed as a stand-alone server.</span></span>

  - <span></span>  
    <span data-ttu-id="5098e-116">**Server Accesso client di Microsoft Exchange Server.**    Le voci con caratteri jolly nel San sono supportate per i client interni ed esterni.</span><span class="sxs-lookup"><span data-stu-id="5098e-116">**Microsoft Exchange Server Client Access server.**   Wildcard entries in the SAN are supported for internal and external clients.</span></span>

  - <span></span>  
    <span data-ttu-id="5098e-117">**Messaggistica unificata di Exchange e server Accesso client di Microsoft Exchange Server sullo stesso server.**    Sono supportate le voci di San con caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="5098e-117">**Exchange Unified Messaging (UM) and Microsoft Exchange Server Client Access server on same server.**   Wildcard SAN entries are supported.</span></span>

<span data-ttu-id="5098e-118">In questo argomento non vengono trattati i ruoli del server seguenti:</span><span class="sxs-lookup"><span data-stu-id="5098e-118">Server roles that are not addressed in this topic:</span></span>

  - <span data-ttu-id="5098e-119">Ruoli del server interni (inclusi, ma non limitati al Mediation Server, all'archiviazione e al Monitoring Server, Survivable Branch Appliance o Survivable Branch Server)</span><span class="sxs-lookup"><span data-stu-id="5098e-119">Internal server roles (including, but not limited to the Mediation Server, Archiving and Monitoring Server, Survivable Branch Appliance, or Survivable Branch Server)</span></span>

  - <span data-ttu-id="5098e-120">Interfacce server perimetrali esterne</span><span class="sxs-lookup"><span data-stu-id="5098e-120">External Edge Server interfaces</span></span>

  - <span data-ttu-id="5098e-121">Server perimetrale interno</span><span class="sxs-lookup"><span data-stu-id="5098e-121">Internal Edge Server</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5098e-122">Per l'interfaccia del server perimetrale interno, è possibile assegnare una voce con caratteri jolly alla rete SAN ed è supportata.</span><span class="sxs-lookup"><span data-stu-id="5098e-122">For the internal Edge Server interface, a wildcard entry can be assigned to the SAN, and is supported.</span></span> <span data-ttu-id="5098e-123">La SAN nel server perimetrale interno non è sottoposta a query e una voce SAN jolly è di valore limitato.</span><span class="sxs-lookup"><span data-stu-id="5098e-123">The SAN on the internal Edge Server is not queried, and a wildcard SAN entry is of limited value.</span></span>

    
    </div>

<span data-ttu-id="5098e-124">Per informazioni dettagliate sulle configurazioni dei certificati, incluso l'utilizzo di caratteri jolly nei certificati, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="5098e-124">For details about certificate configurations, including the use of wildcards in certificates, see the following topics:</span></span>

  - [<span data-ttu-id="5098e-125">Requisiti dei certificati per i server interni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5098e-125">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="5098e-126">Requisiti dei certificati per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5098e-126">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="5098e-127">Riepilogo del certificato-bilanciamento del carico DNS e del caricamento in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5098e-127">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="5098e-128">Riepilogo del certificato-singolo amministratore in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5098e-128">Certificate summary - Single Director in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-director.md)

  - [<span data-ttu-id="5098e-129">Riepilogo del certificato-pool di server Director con scalabilità orizzontale, bilanciamento del carico hardware in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="5098e-129">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="5098e-130">Riepilogo del certificato-proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5098e-130">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="5098e-131">Linee guida per l'integrazione della messaggistica unificata locale e di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5098e-131">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

<span data-ttu-id="5098e-132">Per informazioni dettagliate sulla configurazione dei certificati per Exchange, incluso l'utilizzo di caratteri jolly, vedere la documentazione del prodotto Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="5098e-132">For details about configuring certificates for Exchange, including the use of wildcards, see the Exchange 2013 product documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

