---
title: 'Lync Server 2013: Riepilogo di DNS - singolo server Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca7fea825267dcdc5aa03a2e6c3c9fb3fc26a84b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="25237-102">Riepilogo di DNS - singolo server Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25237-102">DNS summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25237-103">_**Argomento Ultima modifica:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="25237-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="25237-104">La tabella seguente contiene un riepilogo dei record DNS necessari per supportare il singolo Director.</span><span class="sxs-lookup"><span data-stu-id="25237-104">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="25237-105">Il ruolo del Director richiede record DNS simili al server front-end.</span><span class="sxs-lookup"><span data-stu-id="25237-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="25237-106">Il numero di record necessari viene riflesso nei nomi alternativi del soggetto necessari per il certificato Director.</span><span class="sxs-lookup"><span data-stu-id="25237-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="25237-107">Diverso dal server front-end, il Director non ospita gli account utente o ospita i servizi di mobilità.</span><span class="sxs-lookup"><span data-stu-id="25237-107">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="25237-108">Record DNS necessari per il Director</span><span class="sxs-lookup"><span data-stu-id="25237-108">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25237-109">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="25237-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="25237-110">Record FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="25237-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="25237-111">Indirizzo IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="25237-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="25237-112">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="25237-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25237-113">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="25237-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="25237-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="25237-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="25237-115">Director</span><span class="sxs-lookup"><span data-stu-id="25237-115">Director</span></span></p></td>
<td><p><span data-ttu-id="25237-116">Record host Director usato per la replica e il server al server</span><span class="sxs-lookup"><span data-stu-id="25237-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25237-117">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="25237-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="25237-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="25237-118">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="25237-119">Director</span><span class="sxs-lookup"><span data-stu-id="25237-119">Director</span></span></p></td>
<td><p><span data-ttu-id="25237-120">SIP (Session Initiation Protocol) in ingresso dall'interfaccia Edge interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="25237-120">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25237-121">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="25237-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="25237-122">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="25237-122">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="25237-123">Director</span><span class="sxs-lookup"><span data-stu-id="25237-123">Director</span></span></p></td>
<td><p><span data-ttu-id="25237-124">Servizi Web di dialin pubblicati da proxy inverso</span><span class="sxs-lookup"><span data-stu-id="25237-124">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25237-125">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="25237-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="25237-126">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="25237-126">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="25237-127">Director</span><span class="sxs-lookup"><span data-stu-id="25237-127">Director</span></span></p></td>
<td><p><span data-ttu-id="25237-128">Servizi Web pubblicati su Meet proxy inverso</span><span class="sxs-lookup"><span data-stu-id="25237-128">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25237-129">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="25237-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="25237-130">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="25237-130">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="25237-131">Director</span><span class="sxs-lookup"><span data-stu-id="25237-131">Director</span></span></p></td>
<td><p><span data-ttu-id="25237-132">Pubblicato e definito dai servizi Web esterni per i Web Ticket proxy inverso per il direttore</span><span class="sxs-lookup"><span data-stu-id="25237-132">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

