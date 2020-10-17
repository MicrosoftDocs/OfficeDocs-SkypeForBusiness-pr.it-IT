---
title: 'Lync Server 2013: visualizzazione VoIPDetails'
description: 'Lync Server 2013: visualizzazione VoIPDetails.'
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
ms.openlocfilehash: 5ecd34be0c8568eef29d773f088e8503a8065743
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566202"
---
# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="113df-103">Visualizzazione VoIPDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="113df-103">VoIPDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="113df-104">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="113df-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="113df-105">Nella visualizzazione VoIPDetails vengono archiviate le informazioni sulle sessioni peer-to-peer, che contengono almeno un utente VoIP.</span><span class="sxs-lookup"><span data-stu-id="113df-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="113df-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="113df-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="113df-107">La visualizzazione VoIPDetails contiene tutte le colonne della <A href="lync-server-2013-sessiondetails-view.md">Visualizzazione SessionDetails in Lync Server 2013</A> , oltre alle colonne elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="113df-107">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="113df-108">Colonna</span><span class="sxs-lookup"><span data-stu-id="113df-108">Column</span></span></th>
<th><span data-ttu-id="113df-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="113df-109">Data Type</span></span></th>
<th><span data-ttu-id="113df-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="113df-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="113df-111"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="113df-111"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="113df-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="113df-112">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="113df-113">URI telefono dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="113df-113">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="113df-114"><strong>Tophone</strong></span><span class="sxs-lookup"><span data-stu-id="113df-114"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="113df-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="113df-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="113df-116">URI telefono dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="113df-116">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="113df-117"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="113df-117"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="113df-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="113df-118">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="113df-119">URI dell'utente che ha interrotto la sessione.</span><span class="sxs-lookup"><span data-stu-id="113df-119">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="113df-120"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="113df-120"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="113df-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="113df-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="113df-122">Tipo di URI dell'utente che ha interrotto la sessione.</span><span class="sxs-lookup"><span data-stu-id="113df-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="113df-123">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="113df-123">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="113df-124"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="113df-124"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="113df-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="113df-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="113df-126">Tenant dell'utente che ha interrotto la sessione.</span><span class="sxs-lookup"><span data-stu-id="113df-126">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="113df-127"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="113df-127"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="113df-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="113df-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="113df-129">URI telefono dell'utente che ha interrotto la sessione.</span><span class="sxs-lookup"><span data-stu-id="113df-129">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="113df-130"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="113df-130"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="113df-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="113df-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="113df-132">Mediation Server utilizzato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="113df-132">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="113df-133"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="113df-133"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="113df-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="113df-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="113df-135">Mediation Server utilizzato dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="113df-135">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="113df-136"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="113df-136"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="113df-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="113df-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="113df-138">Gateway utilizzato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="113df-138">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="113df-139"><strong>Togateway</strong></span><span class="sxs-lookup"><span data-stu-id="113df-139"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="113df-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="113df-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="113df-141">Gateway utilizzato dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="113df-141">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

