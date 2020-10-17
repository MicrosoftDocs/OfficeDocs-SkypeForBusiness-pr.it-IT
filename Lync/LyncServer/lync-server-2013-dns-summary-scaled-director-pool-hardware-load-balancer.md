---
title: 'Lync Server 2013: pool di directory di riepilogo DNS con scalabilità orizzontale, bilanciamento del carico hardware'
description: 'Lync Server 2013: pool di directory di riepilogo DNS con scalabilità orizzontale, bilanciamento del carico hardware.'
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
ms.openlocfilehash: 7198e6a97feed8ce70cb16753ad1f21d58ef246c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555882"
---
# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="c9c26-103">Pool di server Director con scalabilità verticale di riepilogo DNS, bilanciamento del carico hardware in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="c9c26-103">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9c26-104">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="c9c26-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="c9c26-105">La tabella seguente contiene un riepilogo dei record DNS che sono necessari per supportare il bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="c9c26-105">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="c9c26-106">Il ruolo del Director richiede record DNS simili a quelli del front end server.</span><span class="sxs-lookup"><span data-stu-id="c9c26-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="c9c26-107">Il numero di record necessari viene riflesso nei nomi alternativi del soggetto richiesti per il certificato del server Director.</span><span class="sxs-lookup"><span data-stu-id="c9c26-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="c9c26-108">Diverso dal front end server, il pool di Director non ospita gli account utente o ospita i servizi per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="c9c26-108">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="c9c26-109">Record DNS necessari per il pool di server Director utilizzando un dispositivo di bilanciamento del carico hardware e il bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="c9c26-109">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9c26-110">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="c9c26-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="c9c26-111">FQDN/Record DNS</span><span class="sxs-lookup"><span data-stu-id="c9c26-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="c9c26-112">Indirizzo IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="c9c26-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="c9c26-113">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="c9c26-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9c26-114">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="c9c26-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c9c26-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c9c26-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c9c26-116">Director</span><span class="sxs-lookup"><span data-stu-id="c9c26-116">Director</span></span></p></td>
<td><p><span data-ttu-id="c9c26-117">Record host Director utilizzato per la replica e la comunicazione tra server e server</span><span class="sxs-lookup"><span data-stu-id="c9c26-117">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9c26-118">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="c9c26-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c9c26-119">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="c9c26-119">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="c9c26-120">VIP di HLB del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="c9c26-120">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="c9c26-121">Record host per il pool di server Director con bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="c9c26-121">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9c26-122">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="c9c26-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c9c26-123">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c9c26-123">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c9c26-124">VIP di HLB del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="c9c26-124">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="c9c26-125">SIP (Session Initiation Protocol) in ingresso dall'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="c9c26-125">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9c26-126">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="c9c26-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c9c26-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c9c26-127">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c9c26-128">VIP di HLB del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="c9c26-128">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="c9c26-129">Servizi Web dialin pubblicati con bilanciamento del carico hardware dal proxy inverso</span><span class="sxs-lookup"><span data-stu-id="c9c26-129">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9c26-130">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="c9c26-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c9c26-131">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c9c26-131">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c9c26-132">VIP di HLB del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="c9c26-132">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="c9c26-133">Bilanciamento del carico hardware pubblicato per i servizi Web di meet proxy inverso</span><span class="sxs-lookup"><span data-stu-id="c9c26-133">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9c26-134">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="c9c26-134">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="c9c26-135">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c9c26-135">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="c9c26-136">VIP di HLB del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="c9c26-136">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="c9c26-137">Bilanciamento del carico hardware pubblicato e definito dai servizi Web esterni per il proxy inverso per il pool di server Director</span><span class="sxs-lookup"><span data-stu-id="c9c26-137">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

