---
title: 'Lync Server 2013: pool di directory di riepilogo DNS con scalabilità orizzontale, bilanciamento del carico hardware'
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
ms.openlocfilehash: 7ed4a3a810e4f1aa2fc5228e61cd68af163c91f0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="74c2e-102">Pool di server Director con scalabilità verticale di riepilogo DNS, bilanciamento del carico hardware in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="74c2e-102">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74c2e-103">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="74c2e-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="74c2e-104">La tabella seguente contiene un riepilogo dei record DNS che sono necessari per supportare il bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="74c2e-104">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="74c2e-105">Il ruolo del Director richiede record DNS simili a quelli del front end server.</span><span class="sxs-lookup"><span data-stu-id="74c2e-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="74c2e-106">Il numero di record necessari viene riflesso nei nomi alternativi del soggetto richiesti per il certificato del server Director.</span><span class="sxs-lookup"><span data-stu-id="74c2e-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="74c2e-107">Diverso dal front end server, il pool di Director non ospita gli account utente o ospita i servizi per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="74c2e-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="74c2e-108">Record DNS necessari per il pool di server Director utilizzando un dispositivo di bilanciamento del carico hardware e il bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="74c2e-108">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74c2e-109">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="74c2e-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="74c2e-110">FQDN/Record DNS</span><span class="sxs-lookup"><span data-stu-id="74c2e-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="74c2e-111">Indirizzo IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="74c2e-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="74c2e-112">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="74c2e-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74c2e-113">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="74c2e-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="74c2e-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="74c2e-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="74c2e-115">Director</span><span class="sxs-lookup"><span data-stu-id="74c2e-115">Director</span></span></p></td>
<td><p><span data-ttu-id="74c2e-116">Record host Director utilizzato per la replica e la comunicazione tra server e server</span><span class="sxs-lookup"><span data-stu-id="74c2e-116">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74c2e-117">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="74c2e-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="74c2e-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="74c2e-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="74c2e-119">VIP di HLB del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="74c2e-119">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="74c2e-120">Record host per il pool di server Director con bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="74c2e-120">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74c2e-121">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="74c2e-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="74c2e-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="74c2e-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="74c2e-123">VIP di HLB del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="74c2e-123">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="74c2e-124">SIP (Session Initiation Protocol) in ingresso dall'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="74c2e-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74c2e-125">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="74c2e-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="74c2e-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="74c2e-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="74c2e-127">VIP di HLB del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="74c2e-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="74c2e-128">Servizi Web dialin pubblicati con bilanciamento del carico hardware dal proxy inverso</span><span class="sxs-lookup"><span data-stu-id="74c2e-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74c2e-129">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="74c2e-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="74c2e-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="74c2e-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="74c2e-131">VIP di HLB del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="74c2e-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="74c2e-132">Bilanciamento del carico hardware pubblicato per i servizi Web di meet proxy inverso</span><span class="sxs-lookup"><span data-stu-id="74c2e-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74c2e-133">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="74c2e-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="74c2e-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="74c2e-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="74c2e-135">VIP di HLB del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="74c2e-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="74c2e-136">Bilanciamento del carico hardware pubblicato e definito dai servizi Web esterni per il proxy inverso per il pool di server Director</span><span class="sxs-lookup"><span data-stu-id="74c2e-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

