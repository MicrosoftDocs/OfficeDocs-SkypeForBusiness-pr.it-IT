---
title: 'Lync Server 2013: Tabella Conferences'
description: 'Lync Server 2013: Tabella Conferences.'
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
ms.openlocfilehash: 1e0d8c61e795dc0c8f9843b871d7e4efd1bec571
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561602"
---
# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="81848-103">Tabella Conferences in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81848-103">Conferences table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81848-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="81848-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="81848-105">Ogni record di questa tabella contiene i dettagli sulle chiamate relative a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="81848-105">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81848-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="81848-106">Column</span></span></th>
<th><span data-ttu-id="81848-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="81848-107">Data Type</span></span></th>
<th><span data-ttu-id="81848-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="81848-108">Key/Index</span></span></th>
<th><span data-ttu-id="81848-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="81848-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81848-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="81848-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="81848-111">datetime</span><span class="sxs-lookup"><span data-stu-id="81848-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="81848-112">Principale</span><span class="sxs-lookup"><span data-stu-id="81848-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="81848-113">Ora in cui la richiesta di conferenza è stata acquisita dall'agente di registrazione dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="81848-113">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="81848-114">Viene utilizzata solo come chiave primaria per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="81848-114">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81848-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="81848-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="81848-116">int</span><span class="sxs-lookup"><span data-stu-id="81848-116">int</span></span></p></td>
<td><p><span data-ttu-id="81848-117">Principale</span><span class="sxs-lookup"><span data-stu-id="81848-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="81848-118">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="81848-118">ID number to identify the session.</span></span> <span data-ttu-id="81848-119">Utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco un'istanza di conferenza.</span><span class="sxs-lookup"><span data-stu-id="81848-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81848-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="81848-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="81848-121">int</span><span class="sxs-lookup"><span data-stu-id="81848-121">int</span></span></p></td>
<td><p><span data-ttu-id="81848-122">Stranieri</span><span class="sxs-lookup"><span data-stu-id="81848-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="81848-123">URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="81848-123">Conference URI.</span></span> <span data-ttu-id="81848-124">Per ulteriori informazioni, vedere la <a href="lync-server-2013-conferenceuris-table.md">tabella ConferenceUris in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="81848-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81848-125"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="81848-125"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="81848-126">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="81848-126">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="81848-127">Utile per le conferenze ricorrenti; ogni istanza di una conferenza ricorrente ha lo stesso <strong>ConferenceUri</strong>, ma avrà una <strong>ConfInstance</strong>diversa.</span><span class="sxs-lookup"><span data-stu-id="81848-127">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81848-128"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="81848-128"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="81848-129">datetime</span><span class="sxs-lookup"><span data-stu-id="81848-129">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="81848-130">Ora di inizio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="81848-130">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81848-131"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="81848-131"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="81848-132">datetime</span><span class="sxs-lookup"><span data-stu-id="81848-132">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="81848-133">Ora di inizio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="81848-133">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81848-134"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="81848-134"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="81848-135">int</span><span class="sxs-lookup"><span data-stu-id="81848-135">int</span></span></p></td>
<td><p><span data-ttu-id="81848-136">Stranieri</span><span class="sxs-lookup"><span data-stu-id="81848-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="81848-137">Numero ID per identificare il pool in cui è stata acquisita la conferenza.</span><span class="sxs-lookup"><span data-stu-id="81848-137">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="81848-138">Per ulteriori informazioni, vedere la <a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="81848-138">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81848-139"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="81848-139"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="81848-140">Soglia</span><span class="sxs-lookup"><span data-stu-id="81848-140">Int</span></span></p></td>
<td><p><span data-ttu-id="81848-141">Stranieri</span><span class="sxs-lookup"><span data-stu-id="81848-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="81848-142">Numero ID per identificare l'URI dell'organizzatore della conferenza.</span><span class="sxs-lookup"><span data-stu-id="81848-142">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="81848-143">Per ulteriori informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella users in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="81848-143">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81848-144"><strong>Bandiera</strong></span><span class="sxs-lookup"><span data-stu-id="81848-144"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="81848-145">smallint</span><span class="sxs-lookup"><span data-stu-id="81848-145">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="81848-146">Una maschera di bit che contiene gli attributi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="81848-146">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="81848-147">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="81848-147">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="81848-148">0X01</span><span class="sxs-lookup"><span data-stu-id="81848-148">0X01</span></span></p></li>
<li><p><span data-ttu-id="81848-149">Sintetico</span><span class="sxs-lookup"><span data-stu-id="81848-149">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="81848-150">Transazione</span><span class="sxs-lookup"><span data-stu-id="81848-150">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81848-151"><strong>Elaborati</strong></span><span class="sxs-lookup"><span data-stu-id="81848-151"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="81848-152">po'</span><span class="sxs-lookup"><span data-stu-id="81848-152">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="81848-153">Campo interno utilizzato dal servizio di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="81848-153">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="81848-154">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81848-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="81848-155">\* Per la maggior parte delle sessioni, SessionIdSeq avrà il valore 1.</span><span class="sxs-lookup"><span data-stu-id="81848-155">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="81848-156">Se due sessioni si avviano esattamente nello stesso momento, l'SessionIdSeq per uno sarà 1 e per l'altro sarà 2 e così via.</span><span class="sxs-lookup"><span data-stu-id="81848-156">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

