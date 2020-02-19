---
title: 'Lync Server 2013: visualizzazione VoIPDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5894004244d723d3b233e2963411fdf85b6782ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42118929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="c63cc-102">Visualizzazione VoIPDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c63cc-102">VoIPDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c63cc-103">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="c63cc-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="c63cc-104">Nella visualizzazione VoIPDetails vengono archiviate le informazioni sulle sessioni peer-to-peer, che contengono almeno un utente VoIP.</span><span class="sxs-lookup"><span data-stu-id="c63cc-104">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="c63cc-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c63cc-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c63cc-106">La visualizzazione VoIPDetails contiene tutte le colonne della <A href="lync-server-2013-sessiondetails-view.md">Visualizzazione SessionDetails in Lync Server 2013</A> , oltre alle colonne elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="c63cc-106">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c63cc-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="c63cc-107">Column</span></span></th>
<th><span data-ttu-id="c63cc-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c63cc-108">Data Type</span></span></th>
<th><span data-ttu-id="c63cc-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c63cc-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c63cc-110"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="c63cc-110"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="c63cc-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c63cc-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c63cc-112">URI telefono dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="c63cc-112">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c63cc-113"><strong>Tophone</strong></span><span class="sxs-lookup"><span data-stu-id="c63cc-113"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="c63cc-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c63cc-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c63cc-115">URI telefono dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="c63cc-115">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c63cc-116"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="c63cc-116"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c63cc-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c63cc-117">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c63cc-118">URI dell'utente che ha interrotto la sessione.</span><span class="sxs-lookup"><span data-stu-id="c63cc-118">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c63cc-119"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c63cc-119"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c63cc-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c63cc-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c63cc-121">Tipo di URI dell'utente che ha interrotto la sessione.</span><span class="sxs-lookup"><span data-stu-id="c63cc-121">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="c63cc-122">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c63cc-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c63cc-123"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="c63cc-123"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c63cc-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c63cc-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c63cc-125">Tenant dell'utente che ha interrotto la sessione.</span><span class="sxs-lookup"><span data-stu-id="c63cc-125">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c63cc-126"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="c63cc-126"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="c63cc-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c63cc-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c63cc-128">URI telefono dell'utente che ha interrotto la sessione.</span><span class="sxs-lookup"><span data-stu-id="c63cc-128">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c63cc-129"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="c63cc-129"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="c63cc-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c63cc-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c63cc-131">Mediation Server utilizzato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="c63cc-131">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c63cc-132"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="c63cc-132"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="c63cc-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c63cc-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c63cc-134">Mediation Server utilizzato dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="c63cc-134">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c63cc-135"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="c63cc-135"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="c63cc-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c63cc-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c63cc-137">Gateway utilizzato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="c63cc-137">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c63cc-138"><strong>Togateway</strong></span><span class="sxs-lookup"><span data-stu-id="c63cc-138"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="c63cc-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c63cc-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c63cc-140">Gateway utilizzato dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="c63cc-140">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

