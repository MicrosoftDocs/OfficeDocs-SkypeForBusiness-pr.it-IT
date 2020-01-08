---
title: 'Lync Server 2013: visualizzazione VoIPDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9553be13dcd73f89ba8d6ab051602d378bf353da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="cb94e-102">Visualizzazione VoIPDetails in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb94e-102">VoIPDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb94e-103">_**Argomento Ultima modifica:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="cb94e-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="cb94e-104">La visualizzazione VoIPDetails archivia le informazioni sulle sessioni peer-to-peer, in cui almeno un utente è un utente VoIP.</span><span class="sxs-lookup"><span data-stu-id="cb94e-104">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="cb94e-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb94e-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cb94e-106">La visualizzazione VoIPDetails contiene tutte le colonne della <A href="lync-server-2013-sessiondetails-view.md">Visualizzazione SessionDetails in Lync Server 2013</A> , oltre alle colonne elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="cb94e-106">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb94e-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="cb94e-107">Column</span></span></th>
<th><span data-ttu-id="cb94e-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="cb94e-108">Data Type</span></span></th>
<th><span data-ttu-id="cb94e-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="cb94e-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb94e-110"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="cb94e-110"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="cb94e-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cb94e-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="cb94e-112">URI telefono dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="cb94e-112">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb94e-113"><strong>Telefono</strong></span><span class="sxs-lookup"><span data-stu-id="cb94e-113"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="cb94e-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cb94e-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="cb94e-115">URI telefono dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="cb94e-115">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb94e-116"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="cb94e-116"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="cb94e-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cb94e-117">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="cb94e-118">URI dell'utente che ha scollegato la sessione.</span><span class="sxs-lookup"><span data-stu-id="cb94e-118">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb94e-119"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="cb94e-119"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="cb94e-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cb94e-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cb94e-121">Tipo di URI dell'utente che ha scollegato la sessione.</span><span class="sxs-lookup"><span data-stu-id="cb94e-121">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="cb94e-122">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="cb94e-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb94e-123"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="cb94e-123"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="cb94e-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cb94e-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cb94e-125">Tenant dell'utente che ha scollegato la sessione.</span><span class="sxs-lookup"><span data-stu-id="cb94e-125">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb94e-126"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="cb94e-126"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="cb94e-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cb94e-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="cb94e-128">URI telefono dell'utente che ha scollegato la sessione.</span><span class="sxs-lookup"><span data-stu-id="cb94e-128">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb94e-129"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="cb94e-129"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="cb94e-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cb94e-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cb94e-131">Mediation Server usato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="cb94e-131">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb94e-132"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="cb94e-132"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="cb94e-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cb94e-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cb94e-134">Mediation Server usato dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="cb94e-134">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb94e-135"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="cb94e-135"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="cb94e-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cb94e-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cb94e-137">Gateway usato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="cb94e-137">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb94e-138"><strong>Togateway</strong></span><span class="sxs-lookup"><span data-stu-id="cb94e-138"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="cb94e-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cb94e-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cb94e-140">Gateway usato dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="cb94e-140">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

