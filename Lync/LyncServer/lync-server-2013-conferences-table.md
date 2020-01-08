---
title: 'Lync Server 2013: Tabella Conferences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17cbadaf18fa36ca55f7755b5e679e564163a207
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="c2340-102">Tabella Conferences in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2340-102">Conferences table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2340-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c2340-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c2340-104">Ogni record in questa tabella contiene i dettagli sulle chiamate di una conferenza.</span><span class="sxs-lookup"><span data-stu-id="c2340-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2340-105">Colonna</span><span class="sxs-lookup"><span data-stu-id="c2340-105">Column</span></span></th>
<th><span data-ttu-id="c2340-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c2340-106">Data Type</span></span></th>
<th><span data-ttu-id="c2340-107">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="c2340-107">Key/Index</span></span></th>
<th><span data-ttu-id="c2340-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c2340-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2340-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c2340-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c2340-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="c2340-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="c2340-111">Principale</span><span class="sxs-lookup"><span data-stu-id="c2340-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="c2340-112">Ora in cui la richiesta di conferenza è stata acquisita dall'agente CDR.</span><span class="sxs-lookup"><span data-stu-id="c2340-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="c2340-113">Usato solo come chiave primaria per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="c2340-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2340-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c2340-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c2340-115">int</span><span class="sxs-lookup"><span data-stu-id="c2340-115">int</span></span></p></td>
<td><p><span data-ttu-id="c2340-116">Principale</span><span class="sxs-lookup"><span data-stu-id="c2340-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="c2340-117">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="c2340-117">ID number to identify the session.</span></span> <span data-ttu-id="c2340-118">Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="c2340-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2340-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="c2340-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="c2340-120">int</span><span class="sxs-lookup"><span data-stu-id="c2340-120">int</span></span></p></td>
<td><p><span data-ttu-id="c2340-121">Esterna</span><span class="sxs-lookup"><span data-stu-id="c2340-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c2340-122">URI conferenza.</span><span class="sxs-lookup"><span data-stu-id="c2340-122">Conference URI.</span></span> <span data-ttu-id="c2340-123">Per altre informazioni, vedere la <a href="lync-server-2013-conferenceuris-table.md">tabella ConferenceUris in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c2340-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2340-124"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="c2340-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="c2340-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="c2340-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c2340-126">Utile per le conferenze periodiche; ogni istanza di una conferenza ricorrente ha lo stesso <strong>ConferenceUri</strong>, ma avrà un <strong>ConfInstance</strong>diverso.</span><span class="sxs-lookup"><span data-stu-id="c2340-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2340-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="c2340-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c2340-128">DateTime</span><span class="sxs-lookup"><span data-stu-id="c2340-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c2340-129">Ora di inizio conferenza.</span><span class="sxs-lookup"><span data-stu-id="c2340-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2340-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="c2340-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c2340-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="c2340-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c2340-132">Ora di inizio conferenza.</span><span class="sxs-lookup"><span data-stu-id="c2340-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2340-133"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="c2340-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="c2340-134">int</span><span class="sxs-lookup"><span data-stu-id="c2340-134">int</span></span></p></td>
<td><p><span data-ttu-id="c2340-135">Esterna</span><span class="sxs-lookup"><span data-stu-id="c2340-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c2340-136">Numero ID per identificare il pool in cui è stata acquisita la conferenza.</span><span class="sxs-lookup"><span data-stu-id="c2340-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="c2340-137">Per altre informazioni, vedere la <a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c2340-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2340-138"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="c2340-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c2340-139">Int</span><span class="sxs-lookup"><span data-stu-id="c2340-139">Int</span></span></p></td>
<td><p><span data-ttu-id="c2340-140">Esterna</span><span class="sxs-lookup"><span data-stu-id="c2340-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c2340-141">Numero ID per identificare l'URI dell'organizzatore di questa conferenza.</span><span class="sxs-lookup"><span data-stu-id="c2340-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="c2340-142">Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c2340-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2340-143"><strong>Contrassegno</strong></span><span class="sxs-lookup"><span data-stu-id="c2340-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="c2340-144">smallint</span><span class="sxs-lookup"><span data-stu-id="c2340-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c2340-145">Maschera di bit che contiene gli attributi della conferenza.</span><span class="sxs-lookup"><span data-stu-id="c2340-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="c2340-146">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="c2340-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="c2340-147">0X01</span><span class="sxs-lookup"><span data-stu-id="c2340-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="c2340-148">Sintetico</span><span class="sxs-lookup"><span data-stu-id="c2340-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="c2340-149">Transazione</span><span class="sxs-lookup"><span data-stu-id="c2340-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2340-150"><strong>Elaborate</strong></span><span class="sxs-lookup"><span data-stu-id="c2340-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="c2340-151">po'</span><span class="sxs-lookup"><span data-stu-id="c2340-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c2340-152">Campo interno usato dal servizio di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="c2340-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="c2340-153">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c2340-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c2340-154">\*Per la maggior parte delle sessioni, SessionIdSeq avrà il valore 1.</span><span class="sxs-lookup"><span data-stu-id="c2340-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="c2340-155">Se due sessioni iniziano esattamente nello stesso momento, il SessionIdSeq per uno sarà 1 e per l'altro sarà 2 e così via.</span><span class="sxs-lookup"><span data-stu-id="c2340-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

