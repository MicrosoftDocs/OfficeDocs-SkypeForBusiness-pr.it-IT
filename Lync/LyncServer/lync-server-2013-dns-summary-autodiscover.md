---
title: 'Lync Server 2013: Riepilogo DNS-individuazione automatica'
description: 'Lync Server 2013: sintesi DNS-individuazione automatica.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eef9bd6a2489561145718c7bbf2f710ab0b1f248
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574282"
---
# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="cb3b1-103">Riepilogo DNS-individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb3b1-103">DNS summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb3b1-104">_**Ultimo argomento modificato:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="cb3b1-104">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="cb3b1-105">L'individuazione automatica è un servizio flessibile che accetterà la comunicazione tramite HTTP o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cb3b1-105">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="cb3b1-106">A tale scopo, il DNS (Domain Name System) e i certificati utilizzati dai server che ospitano il servizio di individuazione automatica devono essere configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="cb3b1-106">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="cb3b1-107">I requisiti dei certificati sono descritti in [Riepilogo dei certificati-individuazione automatica in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span><span class="sxs-lookup"><span data-stu-id="cb3b1-107">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cb3b1-108">La logica di ricerca DNS per i client di Lync Server utilizza un ordine di risoluzione specifico.</span><span class="sxs-lookup"><span data-stu-id="cb3b1-108">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="cb3b1-109">È necessario includere sempre entrambi gli LyncdiscoverInternal. &lt; Domain &gt; e lyncdiscover. &lt; dominio &gt; nel DNS.</span><span class="sxs-lookup"><span data-stu-id="cb3b1-109">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="cb3b1-110">Esclusione di LyncdiscoverInternal. &lt; il &gt; record di dominio causerà la mancata connessione dei client interni ai servizi previsti o la ricezione della risposta di individuazione automatica errata.</span><span class="sxs-lookup"><span data-stu-id="cb3b1-110">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="cb3b1-111">Record DNS interni</span><span class="sxs-lookup"><span data-stu-id="cb3b1-111">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb3b1-112">Tipo di record</span><span class="sxs-lookup"><span data-stu-id="cb3b1-112">Record type</span></span></th>
<th><span data-ttu-id="cb3b1-113">Nome host</span><span class="sxs-lookup"><span data-stu-id="cb3b1-113">Host name</span></span></th>
<th><span data-ttu-id="cb3b1-114">Viene risolto in</span><span class="sxs-lookup"><span data-stu-id="cb3b1-114">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb3b1-115">CNAME</span><span class="sxs-lookup"><span data-stu-id="cb3b1-115">CNAME</span></span></p></td>
<td><p><span data-ttu-id="cb3b1-116">LyncdiscoverInternal. &lt; nome di dominio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="cb3b1-116">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="cb3b1-117">FQDN dei servizi Web interni per il pool di server Director, se presente, o per il pool Front End, se non si dispone di un Director.</span><span class="sxs-lookup"><span data-stu-id="cb3b1-117">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb3b1-118">A (host, se IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="cb3b1-118">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="cb3b1-119">LyncdiscoverInternal. &lt; nome di dominio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="cb3b1-119">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="cb3b1-120">Indirizzo IP dei servizi Web interni (indirizzo IP virtuale (VIP) se si utilizza un servizio di bilanciamento del carico) del pool di server Director, se si dispone di uno o del pool Front End, se non si dispone di un Director.</span><span class="sxs-lookup"><span data-stu-id="cb3b1-120">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cb3b1-121">È necessario creare uno dei record DNS esterni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cb3b1-121">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="cb3b1-122">Record DNS esterni</span><span class="sxs-lookup"><span data-stu-id="cb3b1-122">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb3b1-123">Tipo di record</span><span class="sxs-lookup"><span data-stu-id="cb3b1-123">Record type</span></span></th>
<th><span data-ttu-id="cb3b1-124">Nome host</span><span class="sxs-lookup"><span data-stu-id="cb3b1-124">Host name</span></span></th>
<th><span data-ttu-id="cb3b1-125">Viene risolto in</span><span class="sxs-lookup"><span data-stu-id="cb3b1-125">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb3b1-126">CNAME</span><span class="sxs-lookup"><span data-stu-id="cb3b1-126">CNAME</span></span></p></td>
<td><p><span data-ttu-id="cb3b1-127">lyncdiscover. &lt; SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="cb3b1-127">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="cb3b1-128">FQDN dei servizi Web esterni per il pool di server Director, se presente, o per il pool Front End, se non si dispone di un Director.</span><span class="sxs-lookup"><span data-stu-id="cb3b1-128">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb3b1-129">A (host, se IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="cb3b1-129">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="cb3b1-130">lyncdiscover. &lt; SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="cb3b1-130">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="cb3b1-131">Indirizzo IP esterno o pubblico del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="cb3b1-131">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="cb3b1-132">Il traffico esterno passa attraverso il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="cb3b1-132">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="cb3b1-133">I client dei dispositivi mobili non supportano certificati SSL (Secure Sockets Layer) multipli da domini diversi.</span><span class="sxs-lookup"><span data-stu-id="cb3b1-133">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="cb3b1-134">Di conseguenza, il reindirizzamento CNAME a domini diversi non è supportato in HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cb3b1-134">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="cb3b1-135">Ad esempio, un record CNAME DNS per lyncdiscover.contoso.com che esegue il reindirizzamento a un indirizzo director.contoso.net non è supportato in HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cb3b1-135">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="cb3b1-136">In una topologia di questo tipo, un client di dispositivo portatile deve utilizzare il protocollo HTTP per la prima richiesta, in modo che il reindirizzamento CNAME venga risolto in HTTP.</span><span class="sxs-lookup"><span data-stu-id="cb3b1-136">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="cb3b1-137">Per le richieste successive viene quindi utilizzato HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cb3b1-137">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="cb3b1-138">Per supportare questo scenario, è necessario configurare il proxy inverso con una regola di pubblicazione Web per la porta 80 (HTTP).</span><span class="sxs-lookup"><span data-stu-id="cb3b1-138">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="cb3b1-139">Per informazioni dettagliate, vedere la sezione relativa alla creazione di una regola di pubblicazione Web per la porta 80 in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">configurazione del proxy inverso per i dispositivi mobili in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cb3b1-139">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="cb3b1-140">Il reindirizzamento CNAME allo stesso dominio è supportato in HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cb3b1-140">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="cb3b1-141">In questo caso, il certificato del dominio di destinazione copre il dominio di origine.</span><span class="sxs-lookup"><span data-stu-id="cb3b1-141">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cb3b1-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb3b1-142">See Also</span></span>


[<span data-ttu-id="cb3b1-143">Configurazione del proxy inverso per i dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb3b1-143">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="cb3b1-144">Riepilogo del certificato-individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb3b1-144">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

