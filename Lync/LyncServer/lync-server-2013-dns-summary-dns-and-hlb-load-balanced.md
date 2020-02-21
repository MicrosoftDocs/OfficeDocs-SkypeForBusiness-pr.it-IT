---
title: 'Lync Server 2013: Riepilogo DNS-bilanciamento del carico DNS'
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
ms.openlocfilehash: 86a4b90cc78b3fdcb6b5a02332d95468f8246c84
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="80eb5-102">Riepilogo DNS-bilanciamento del carico DNS e del caricamento in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80eb5-102">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80eb5-103">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="80eb5-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="80eb5-104">La tabella seguente contiene un riepilogo dei record DNS che sono necessari per supportare il bilanciamento del carico DNS e il bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="80eb5-104">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="80eb5-105">Il ruolo del Director richiede record DNS simili a quelli del front end server.</span><span class="sxs-lookup"><span data-stu-id="80eb5-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="80eb5-106">Il numero di record necessari viene riflesso nei nomi alternativi del soggetto richiesti per il certificato del server Director.</span><span class="sxs-lookup"><span data-stu-id="80eb5-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="80eb5-107">Diverso dal front end server, il pool di Director non ospita gli account utente o ospita i servizi per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="80eb5-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="80eb5-108">Record DNS necessari per il pool di server Director tramite bilanciamento del carico DNS e bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="80eb5-108">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80eb5-109">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="80eb5-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="80eb5-110">FQDN/Record DNS</span><span class="sxs-lookup"><span data-stu-id="80eb5-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="80eb5-111">Indirizzo IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="80eb5-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="80eb5-112">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="80eb5-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80eb5-113">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="80eb5-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="80eb5-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="80eb5-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="80eb5-115">Director</span><span class="sxs-lookup"><span data-stu-id="80eb5-115">Director</span></span></p></td>
<td><p><span data-ttu-id="80eb5-116">Record host Director utilizzato per la replica e il server in server</span><span class="sxs-lookup"><span data-stu-id="80eb5-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80eb5-117">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="80eb5-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="80eb5-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="80eb5-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="80eb5-119">Pool Director</span><span class="sxs-lookup"><span data-stu-id="80eb5-119">Director pool</span></span></p></td>
<td><p><span data-ttu-id="80eb5-120">Record host per il pool di server Director con bilanciamento del carico DNS</span><span class="sxs-lookup"><span data-stu-id="80eb5-120">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80eb5-121">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="80eb5-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="80eb5-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80eb5-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="80eb5-123">Pool Director</span><span class="sxs-lookup"><span data-stu-id="80eb5-123">Director pool</span></span></p></td>
<td><p><span data-ttu-id="80eb5-124">SIP (Session Initiation Protocol) in ingresso dall'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="80eb5-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80eb5-125">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="80eb5-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="80eb5-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80eb5-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="80eb5-127">VIP di HLB del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="80eb5-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="80eb5-128">Servizi Web dialin pubblicati con bilanciamento del carico hardware dal proxy inverso</span><span class="sxs-lookup"><span data-stu-id="80eb5-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80eb5-129">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="80eb5-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="80eb5-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80eb5-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="80eb5-131">VIP di HLB del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="80eb5-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="80eb5-132">Bilanciamento del carico hardware pubblicato per i servizi Web di meet proxy inverso</span><span class="sxs-lookup"><span data-stu-id="80eb5-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80eb5-133">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="80eb5-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="80eb5-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80eb5-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="80eb5-135">VIP di HLB del pool di server Director</span><span class="sxs-lookup"><span data-stu-id="80eb5-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="80eb5-136">Bilanciamento del carico hardware pubblicato e definito dai servizi Web esterni per il proxy inverso per il pool di server Director</span><span class="sxs-lookup"><span data-stu-id="80eb5-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

