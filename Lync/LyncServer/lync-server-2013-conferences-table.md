---
title: 'Lync Server 2013: Tabella Conferences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8cbb42d078ccba029ae0cf55c7b1ced803aa94f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="03064-102">Tabella Conferences in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03064-102">Conferences table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03064-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="03064-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="03064-104">Ogni record di questa tabella contiene i dettagli sulle chiamate relative a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="03064-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03064-105">Colonna</span><span class="sxs-lookup"><span data-stu-id="03064-105">Column</span></span></th>
<th><span data-ttu-id="03064-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="03064-106">Data Type</span></span></th>
<th><span data-ttu-id="03064-107">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="03064-107">Key/Index</span></span></th>
<th><span data-ttu-id="03064-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="03064-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03064-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="03064-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="03064-110">datetime</span><span class="sxs-lookup"><span data-stu-id="03064-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="03064-111">Principale</span><span class="sxs-lookup"><span data-stu-id="03064-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="03064-112">Ora in cui la richiesta di conferenza è stata acquisita dall'agente di registrazione dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="03064-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="03064-113">Viene utilizzata solo come chiave primaria per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="03064-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03064-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="03064-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="03064-115">int</span><span class="sxs-lookup"><span data-stu-id="03064-115">int</span></span></p></td>
<td><p><span data-ttu-id="03064-116">Principale</span><span class="sxs-lookup"><span data-stu-id="03064-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="03064-117">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="03064-117">ID number to identify the session.</span></span> <span data-ttu-id="03064-118">Utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="03064-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03064-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="03064-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="03064-120">int</span><span class="sxs-lookup"><span data-stu-id="03064-120">int</span></span></p></td>
<td><p><span data-ttu-id="03064-121">Stranieri</span><span class="sxs-lookup"><span data-stu-id="03064-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="03064-122">URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="03064-122">Conference URI.</span></span> <span data-ttu-id="03064-123">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferenceuris-table.md">tabella ConferenceUris in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="03064-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03064-124"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="03064-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="03064-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="03064-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="03064-126">Utile per le conferenze ricorrenti; ogni istanza di una conferenza ricorrente ha lo stesso <strong>ConferenceUri</strong>, ma avrà una <strong>ConfInstance</strong>diversa.</span><span class="sxs-lookup"><span data-stu-id="03064-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03064-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="03064-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="03064-128">datetime</span><span class="sxs-lookup"><span data-stu-id="03064-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="03064-129">Ora di inizio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="03064-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03064-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="03064-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="03064-131">datetime</span><span class="sxs-lookup"><span data-stu-id="03064-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="03064-132">Ora di inizio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="03064-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03064-133"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="03064-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="03064-134">int</span><span class="sxs-lookup"><span data-stu-id="03064-134">int</span></span></p></td>
<td><p><span data-ttu-id="03064-135">Stranieri</span><span class="sxs-lookup"><span data-stu-id="03064-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="03064-136">Numero ID per identificare il pool in cui è stata acquisita la conferenza.</span><span class="sxs-lookup"><span data-stu-id="03064-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="03064-137">Per ulteriori informazioni, vedere la <a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="03064-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03064-138"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="03064-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="03064-139">Soglia</span><span class="sxs-lookup"><span data-stu-id="03064-139">Int</span></span></p></td>
<td><p><span data-ttu-id="03064-140">Stranieri</span><span class="sxs-lookup"><span data-stu-id="03064-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="03064-141">Numero ID per identificare l'URI dell'organizzatore della conferenza.</span><span class="sxs-lookup"><span data-stu-id="03064-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="03064-142">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="03064-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03064-143"><strong>Bandiera</strong></span><span class="sxs-lookup"><span data-stu-id="03064-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="03064-144">smallint</span><span class="sxs-lookup"><span data-stu-id="03064-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="03064-145">Una maschera di bit che contiene gli attributi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="03064-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="03064-146">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="03064-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="03064-147">0X01</span><span class="sxs-lookup"><span data-stu-id="03064-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="03064-148">Sintetico</span><span class="sxs-lookup"><span data-stu-id="03064-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="03064-149">Transazione</span><span class="sxs-lookup"><span data-stu-id="03064-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03064-150"><strong>Elaborati</strong></span><span class="sxs-lookup"><span data-stu-id="03064-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="03064-151">po'</span><span class="sxs-lookup"><span data-stu-id="03064-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="03064-152">Campo interno utilizzato dal servizio di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="03064-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="03064-153">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03064-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="03064-154">\*Per la maggior parte delle sessioni, SessionIdSeq avrà il valore 1.</span><span class="sxs-lookup"><span data-stu-id="03064-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="03064-155">Se due sessioni si avviano esattamente nello stesso momento, l'SessionIdSeq per uno sarà 1 e per l'altro sarà 2 e così via.</span><span class="sxs-lookup"><span data-stu-id="03064-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

