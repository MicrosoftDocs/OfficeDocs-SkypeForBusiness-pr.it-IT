---
title: 'Lync Server 2013: Riepilogo DNS-individuazione automatica'
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
ms.openlocfilehash: 236a3625b755697580e57c926dd5714a44c0347f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="d1924-102">Riepilogo DNS-individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1924-102">DNS summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1924-103">_**Ultimo argomento modificato:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="d1924-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="d1924-104">L'individuazione automatica è un servizio flessibile che accetterà la comunicazione tramite HTTP o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d1924-104">Autodiscover is a flexible service in that it will accept communication over HTTP or HTTPS.</span></span> <span data-ttu-id="d1924-105">A tale scopo, il DNS (Domain Name System) e i certificati utilizzati dai server che ospitano il servizio di individuazione automatica devono essere configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="d1924-105">To accomplish this, the domain name system (DNS) and the certificates used by servers that host the Autodiscover service must be configured correctly.</span></span> <span data-ttu-id="d1924-106">I requisiti dei certificati sono descritti in [Riepilogo dei certificati-individuazione automatica in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span><span class="sxs-lookup"><span data-stu-id="d1924-106">Certificate requirements are covered in [Certificate summary - Autodiscover in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d1924-107">La logica di ricerca DNS per i client di Lync Server utilizza un ordine di risoluzione specifico.</span><span class="sxs-lookup"><span data-stu-id="d1924-107">DNS lookup logic for the Lync Server clients uses a specific order of resolution.</span></span> <span data-ttu-id="d1924-108">È necessario includere sempre entrambi gli LyncdiscoverInternal. &lt;domain&gt; e lyncdiscover. &lt;dominio&gt; nel DNS.</span><span class="sxs-lookup"><span data-stu-id="d1924-108">You should always include both the lyncdiscoverinternal.&lt;domain&gt; and the lyncdiscover.&lt;domain&gt; in your DNS.</span></span> <span data-ttu-id="d1924-109">Esclusione di LyncdiscoverInternal. &lt;il&gt; record di dominio causerà la mancata connessione dei client interni ai servizi previsti o la ricezione della risposta di individuazione automatica errata.</span><span class="sxs-lookup"><span data-stu-id="d1924-109">Excluding the lyncdiscoverinternal.&lt;domain&gt; record will cause internal clients to fail to connect to the intended services or receive the incorrect Autodiscover response.</span></span>



</div>

### <a name="internal-dns-records"></a><span data-ttu-id="d1924-110">Record DNS interni</span><span class="sxs-lookup"><span data-stu-id="d1924-110">Internal DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1924-111">Tipo di record</span><span class="sxs-lookup"><span data-stu-id="d1924-111">Record type</span></span></th>
<th><span data-ttu-id="d1924-112">Nome host</span><span class="sxs-lookup"><span data-stu-id="d1924-112">Host name</span></span></th>
<th><span data-ttu-id="d1924-113">Viene risolto in</span><span class="sxs-lookup"><span data-stu-id="d1924-113">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1924-114">CNAME</span><span class="sxs-lookup"><span data-stu-id="d1924-114">CNAME</span></span></p></td>
<td><p><span data-ttu-id="d1924-115">LyncdiscoverInternal. &lt;nome di dominio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="d1924-115">Lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="d1924-116">FQDN dei servizi Web interni per il pool di server Director, se presente, o per il pool Front End, se non si dispone di un Director.</span><span class="sxs-lookup"><span data-stu-id="d1924-116">Internal Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1924-117">A (host, se IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="d1924-117">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="d1924-118">LyncdiscoverInternal. &lt;nome di dominio interno&gt;</span><span class="sxs-lookup"><span data-stu-id="d1924-118">lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
<td><p><span data-ttu-id="d1924-119">Indirizzo IP dei servizi Web interni (indirizzo IP virtuale (VIP) se si utilizza un servizio di bilanciamento del carico) del pool di server Director, se si dispone di uno o del pool Front End, se non si dispone di un Director.</span><span class="sxs-lookup"><span data-stu-id="d1924-119">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d1924-120">È necessario creare uno dei record DNS esterni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1924-120">You need to create one of the following external DNS records:</span></span>

### <a name="external-dns-records"></a><span data-ttu-id="d1924-121">Record DNS esterni</span><span class="sxs-lookup"><span data-stu-id="d1924-121">External DNS Records</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1924-122">Tipo di record</span><span class="sxs-lookup"><span data-stu-id="d1924-122">Record type</span></span></th>
<th><span data-ttu-id="d1924-123">Nome host</span><span class="sxs-lookup"><span data-stu-id="d1924-123">Host name</span></span></th>
<th><span data-ttu-id="d1924-124">Viene risolto in</span><span class="sxs-lookup"><span data-stu-id="d1924-124">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1924-125">CNAME</span><span class="sxs-lookup"><span data-stu-id="d1924-125">CNAME</span></span></p></td>
<td><p><span data-ttu-id="d1924-126">Lyncdiscover. &lt;SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="d1924-126">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="d1924-127">FQDN dei servizi Web esterni per il pool di server Director, se presente, o per il pool Front End, se non si dispone di un Director.</span><span class="sxs-lookup"><span data-stu-id="d1924-127">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1924-128">A (host, se IPv6, AAAA)</span><span class="sxs-lookup"><span data-stu-id="d1924-128">A (host, if IPv6, AAAA)</span></span></p></td>
<td><p><span data-ttu-id="d1924-129">Lyncdiscover. &lt;SipDomain&gt;</span><span class="sxs-lookup"><span data-stu-id="d1924-129">lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="d1924-130">Indirizzo IP esterno o pubblico del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="d1924-130">External or public IP address of the reverse proxy.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="d1924-131">Il traffico esterno passa attraverso il proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="d1924-131">External traffic goes through the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d1924-132">I client dei dispositivi mobili non supportano certificati SSL (Secure Sockets Layer) multipli da domini diversi.</span><span class="sxs-lookup"><span data-stu-id="d1924-132">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="d1924-133">Di conseguenza, il reindirizzamento CNAME a domini diversi non è supportato in HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d1924-133">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="d1924-134">Ad esempio, un record CNAME DNS per lyncdiscover.contoso.com che esegue il reindirizzamento a un indirizzo director.contoso.net non è supportato in HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d1924-134">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="d1924-135">In una topologia di questo tipo, un client di dispositivo portatile deve utilizzare il protocollo HTTP per la prima richiesta, in modo che il reindirizzamento CNAME venga risolto in HTTP.</span><span class="sxs-lookup"><span data-stu-id="d1924-135">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="d1924-136">Per le richieste successive viene quindi utilizzato HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d1924-136">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="d1924-137">Per supportare questo scenario, è necessario configurare il proxy inverso con una regola di pubblicazione Web per la porta 80 (HTTP).</span><span class="sxs-lookup"><span data-stu-id="d1924-137">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="d1924-138">Per informazioni dettagliate, vedere la sezione relativa alla creazione di una regola di pubblicazione Web per la porta 80 in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">configurazione del proxy inverso per i dispositivi mobili in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d1924-138">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span> <span data-ttu-id="d1924-139">Il reindirizzamento CNAME allo stesso dominio è supportato in HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d1924-139">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="d1924-140">In questo caso, il certificato del dominio di destinazione copre il dominio di origine.</span><span class="sxs-lookup"><span data-stu-id="d1924-140">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d1924-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1924-141">See Also</span></span>


[<span data-ttu-id="d1924-142">Configurazione del proxy inverso per i dispositivi mobili in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1924-142">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[<span data-ttu-id="d1924-143">Riepilogo del certificato-individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1924-143">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

