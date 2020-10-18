---
title: 'Lync Server 2013: Riepilogo DNS-bilanciamento del carico DNS'
description: 'Lync Server 2013: Riepilogo DNS-bilanciamento del carico DNS e del caricamento del sistema.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81c191d653ce4025618e135b4c69bc673f79a6d9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574262"
---
# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="35235-103">Riepilogo DNS-bilanciamento del carico DNS e del caricamento in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35235-103">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35235-104">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="35235-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="35235-105">La tabella seguente contiene un riepilogo dei record DNS che sono necessari per supportare il bilanciamento del carico DNS e il bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="35235-105">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="35235-106">Il ruolo del Director richiede record DNS simili a quelli del front end server.</span><span class="sxs-lookup"><span data-stu-id="35235-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="35235-107">Il numero di record necessari viene riflesso nei nomi alternativi del soggetto richiesti per il certificato del server Director.</span><span class="sxs-lookup"><span data-stu-id="35235-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="35235-108">Diverso dal front end server, il pool di Director non ospita gli account utente o ospita i servizi per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="35235-108">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="35235-109">Record DNS necessari per il pool di server Director tramite bilanciamento del carico DNS e bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="35235-109">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35235-110">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="35235-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="35235-111">FQDN/Record DNS</span><span class="sxs-lookup"><span data-stu-id="35235-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="35235-112">Indirizzo IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="35235-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="35235-113">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="35235-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="35235-114">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="35235-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="35235-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="35235-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="35235-116">Director</span><span class="sxs-lookup"><span data-stu-id="35235-116">Director</span></span></p></td>
<td><p><span data-ttu-id="35235-117">Record host Director utilizzato per la replica e il server in server</span><span class="sxs-lookup"><span data-stu-id="35235-117">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35235-118">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="35235-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="35235-119">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="35235-119">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="35235-120">Pool Director</span><span class="sxs-lookup"><span data-stu-id="35235-120">Director pool</span></span></p></td>
<td><p><span data-ttu-id="35235-121">Record host per il pool di server Director con bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="35235-121">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35235-122">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="35235-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="35235-123">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="35235-123">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="35235-124">Pool Director</span><span class="sxs-lookup"><span data-stu-id="35235-124">Director pool</span></span></p></td>
<td><p><span data-ttu-id="35235-125">SIP (Session Initiation Protocol) in ingresso dall'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="35235-125">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35235-126">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="35235-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="35235-127">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="35235-127">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="35235-128">VIP di HLB del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="35235-128">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="35235-129">Servizi Web dialin pubblicati con bilanciamento del carico hardware dal proxy inverso</span><span class="sxs-lookup"><span data-stu-id="35235-129">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="35235-130">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="35235-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="35235-131">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="35235-131">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="35235-132">VIP di HLB del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="35235-132">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="35235-133">Bilanciamento del carico hardware pubblicato per i servizi Web di meet proxy inverso</span><span class="sxs-lookup"><span data-stu-id="35235-133">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="35235-134">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="35235-134">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="35235-135">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="35235-135">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="35235-136">VIP di HLB del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="35235-136">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="35235-137">Bilanciamento del carico hardware pubblicato e definito dai servizi Web esterni per il proxy inverso per il pool di server Director</span><span class="sxs-lookup"><span data-stu-id="35235-137">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

