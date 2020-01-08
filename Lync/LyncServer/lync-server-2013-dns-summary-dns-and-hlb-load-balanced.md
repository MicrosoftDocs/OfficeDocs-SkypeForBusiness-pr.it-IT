---
title: 'Lync Server 2013: Riepilogo di DNS - bilanciamento del carico DNS e bilanciamento del carico hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceccb52a8ef9fae810821ffe6b52b763dd8904c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="4197a-102">Riepilogo di DNS - bilanciamento del carico DNS e bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4197a-102">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4197a-103">_**Argomento Ultima modifica:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="4197a-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="4197a-104">La tabella seguente contiene un riepilogo dei record DNS necessari per supportare il bilanciamento del carico DNS e del Director di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="4197a-104">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="4197a-105">Il ruolo del Director richiede record DNS simili al server front-end.</span><span class="sxs-lookup"><span data-stu-id="4197a-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="4197a-106">Il numero di record necessari viene riflesso nei nomi alternativi del soggetto necessari per il certificato Director.</span><span class="sxs-lookup"><span data-stu-id="4197a-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="4197a-107">Diverso dal server front-end, il pool di Director non ospita gli account utente o ospita i servizi mobili.</span><span class="sxs-lookup"><span data-stu-id="4197a-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="4197a-108">Record DNS necessari per il pool di Director con il bilanciamento del carico DNS e il bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="4197a-108">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4197a-109">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="4197a-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="4197a-110">Record FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="4197a-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="4197a-111">Indirizzo IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="4197a-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="4197a-112">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="4197a-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4197a-113">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="4197a-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4197a-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4197a-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="4197a-115">Director</span><span class="sxs-lookup"><span data-stu-id="4197a-115">Director</span></span></p></td>
<td><p><span data-ttu-id="4197a-116">Record host Director usato per la replica e il server al server</span><span class="sxs-lookup"><span data-stu-id="4197a-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4197a-117">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="4197a-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4197a-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="4197a-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="4197a-119">Pool di Director</span><span class="sxs-lookup"><span data-stu-id="4197a-119">Director pool</span></span></p></td>
<td><p><span data-ttu-id="4197a-120">Record host per il pool di Director di bilanciamento del carico DNS per server in server</span><span class="sxs-lookup"><span data-stu-id="4197a-120">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4197a-121">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="4197a-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4197a-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4197a-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4197a-123">Pool di Director</span><span class="sxs-lookup"><span data-stu-id="4197a-123">Director pool</span></span></p></td>
<td><p><span data-ttu-id="4197a-124">SIP (Session Initiation Protocol) in ingresso dall'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="4197a-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4197a-125">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="4197a-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4197a-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4197a-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4197a-127">Pool Director HLB VIP</span><span class="sxs-lookup"><span data-stu-id="4197a-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="4197a-128">Servizi Web di dialin con bilanciamento del carico hardware pubblicati da proxy inverso</span><span class="sxs-lookup"><span data-stu-id="4197a-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4197a-129">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="4197a-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4197a-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4197a-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4197a-131">Pool Director HLB VIP</span><span class="sxs-lookup"><span data-stu-id="4197a-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="4197a-132">Bilanciamento del carico hardware pubblicato per soddisfare i servizi Web da proxy inverso</span><span class="sxs-lookup"><span data-stu-id="4197a-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4197a-133">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="4197a-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="4197a-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4197a-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4197a-135">Pool Director HLB VIP</span><span class="sxs-lookup"><span data-stu-id="4197a-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="4197a-136">Bilanciamento del carico hardware pubblicato e definito dai servizi Web esterni del proxy inverso per il pool di Director</span><span class="sxs-lookup"><span data-stu-id="4197a-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

