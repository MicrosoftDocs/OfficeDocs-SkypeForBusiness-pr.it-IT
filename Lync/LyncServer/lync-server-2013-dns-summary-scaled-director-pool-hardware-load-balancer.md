---
title: 'Lync Server 2013: Riepilogo di DNS - pool di server Director con scalabilità implementata, servizio di bilanciamento del carico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 891b69339416c81d81e72e43edf5f09bbf9da3e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="daf01-102">Riepilogo di DNS - pool di server Director con scalabilità implementata, servizio di bilanciamento del carico in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="daf01-102">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="daf01-103">_**Argomento Ultima modifica:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="daf01-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="daf01-104">La tabella seguente contiene un riepilogo dei record DNS necessari per il supporto del Director di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="daf01-104">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="daf01-105">Il ruolo del Director richiede record DNS simili al server front-end.</span><span class="sxs-lookup"><span data-stu-id="daf01-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="daf01-106">Il numero di record necessari viene riflesso nei nomi alternativi del soggetto necessari per il certificato Director.</span><span class="sxs-lookup"><span data-stu-id="daf01-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="daf01-107">Diverso dal server front-end, il pool di Director non ospita gli account utente o ospita i servizi mobili.</span><span class="sxs-lookup"><span data-stu-id="daf01-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="daf01-108">Record DNS necessari per il pool di Director con un bilanciamento del carico hardware e un bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="daf01-108">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="daf01-109">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="daf01-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="daf01-110">Record FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="daf01-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="daf01-111">Indirizzo IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="daf01-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="daf01-112">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="daf01-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daf01-113">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="daf01-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="daf01-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="daf01-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="daf01-115">Director</span><span class="sxs-lookup"><span data-stu-id="daf01-115">Director</span></span></p></td>
<td><p><span data-ttu-id="daf01-116">Record host Director usato per la replica e la comunicazione da server a server</span><span class="sxs-lookup"><span data-stu-id="daf01-116">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daf01-117">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="daf01-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="daf01-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="daf01-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="daf01-119">Pool Director HLB VIP</span><span class="sxs-lookup"><span data-stu-id="daf01-119">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="daf01-120">Record host per il pool di Director di bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="daf01-120">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daf01-121">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="daf01-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="daf01-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="daf01-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="daf01-123">Pool Director HLB VIP</span><span class="sxs-lookup"><span data-stu-id="daf01-123">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="daf01-124">SIP (Session Initiation Protocol) in ingresso dall'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="daf01-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daf01-125">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="daf01-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="daf01-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="daf01-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="daf01-127">Pool Director HLB VIP</span><span class="sxs-lookup"><span data-stu-id="daf01-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="daf01-128">Servizi Web di dialin con bilanciamento del carico hardware pubblicati da proxy inverso</span><span class="sxs-lookup"><span data-stu-id="daf01-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daf01-129">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="daf01-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="daf01-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="daf01-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="daf01-131">Pool Director HLB VIP</span><span class="sxs-lookup"><span data-stu-id="daf01-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="daf01-132">Bilanciamento del carico hardware pubblicato per soddisfare i servizi Web da proxy inverso</span><span class="sxs-lookup"><span data-stu-id="daf01-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daf01-133">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="daf01-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="daf01-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="daf01-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="daf01-135">Pool Director HLB VIP</span><span class="sxs-lookup"><span data-stu-id="daf01-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="daf01-136">Bilanciamento del carico hardware pubblicato e definito dai servizi Web esterni del proxy inverso per il pool di Director</span><span class="sxs-lookup"><span data-stu-id="daf01-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

