---
title: 'Lync Server 2013: Riepilogo DNS-singolo server Director'
description: 'Lync Server 2013: Riepilogo DNS-singolo server Director.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78ef19383df45644ad951ca5da69ef893b231980
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553232"
---
# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="98b8f-103">Riepilogo DNS-singolo Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98b8f-103">DNS summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98b8f-104">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="98b8f-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="98b8f-105">La tabella seguente contiene un riepilogo dei record DNS necessari per il supporto del singolo Director.</span><span class="sxs-lookup"><span data-stu-id="98b8f-105">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="98b8f-106">Il ruolo del Director richiede record DNS simili a quelli del front end server.</span><span class="sxs-lookup"><span data-stu-id="98b8f-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="98b8f-107">Il numero di record necessari viene riflesso nei nomi alternativi del soggetto richiesti per il certificato del server Director.</span><span class="sxs-lookup"><span data-stu-id="98b8f-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="98b8f-108">Diverso dal front end server, il Director non ospita gli account utente o ospita i servizi per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="98b8f-108">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="98b8f-109">Record DNS necessari per il server Director</span><span class="sxs-lookup"><span data-stu-id="98b8f-109">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98b8f-110">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="98b8f-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="98b8f-111">FQDN/Record DNS</span><span class="sxs-lookup"><span data-stu-id="98b8f-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="98b8f-112">Indirizzo IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="98b8f-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="98b8f-113">Mapping a/Commenti</span><span class="sxs-lookup"><span data-stu-id="98b8f-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98b8f-114">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="98b8f-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="98b8f-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="98b8f-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="98b8f-116">Director</span><span class="sxs-lookup"><span data-stu-id="98b8f-116">Director</span></span></p></td>
<td><p><span data-ttu-id="98b8f-117">Record host Director utilizzato per la replica e il server in server</span><span class="sxs-lookup"><span data-stu-id="98b8f-117">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98b8f-118">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="98b8f-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="98b8f-119">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98b8f-119">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="98b8f-120">Director</span><span class="sxs-lookup"><span data-stu-id="98b8f-120">Director</span></span></p></td>
<td><p><span data-ttu-id="98b8f-121">SIP (Session Initiation Protocol) in ingresso dall'interfaccia perimetrale interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="98b8f-121">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98b8f-122">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="98b8f-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="98b8f-123">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98b8f-123">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="98b8f-124">Director</span><span class="sxs-lookup"><span data-stu-id="98b8f-124">Director</span></span></p></td>
<td><p><span data-ttu-id="98b8f-125">Servizi Web Accesso esterno pubblicati da proxy inverso</span><span class="sxs-lookup"><span data-stu-id="98b8f-125">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98b8f-126">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="98b8f-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="98b8f-127">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98b8f-127">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="98b8f-128">Director</span><span class="sxs-lookup"><span data-stu-id="98b8f-128">Director</span></span></p></td>
<td><p><span data-ttu-id="98b8f-129">Servizi Web Accesso Riunione pubblicati da proxy inverso</span><span class="sxs-lookup"><span data-stu-id="98b8f-129">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98b8f-130">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="98b8f-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="98b8f-131">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98b8f-131">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="98b8f-132">Director</span><span class="sxs-lookup"><span data-stu-id="98b8f-132">Director</span></span></p></td>
<td><p><span data-ttu-id="98b8f-133">Pubblicati e definiti dai servizi Web esterni per il proxy inverso per il server Director</span><span class="sxs-lookup"><span data-stu-id="98b8f-133">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

