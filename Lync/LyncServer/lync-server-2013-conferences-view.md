---
title: 'Lync Server 2013: visualizzazione conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 710aadb2770e9389d9e4becf206d68b8e8d815ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="e6f92-102">Visualizzazione conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6f92-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6f92-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e6f92-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e6f92-104">La visualizzazione conferenze archivia le informazioni sulle conferenze.</span><span class="sxs-lookup"><span data-stu-id="e6f92-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="e6f92-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6f92-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6f92-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="e6f92-106">Column</span></span></th>
<th><span data-ttu-id="e6f92-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="e6f92-107">Data Type</span></span></th>
<th><span data-ttu-id="e6f92-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e6f92-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6f92-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e6f92-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e6f92-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6f92-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="e6f92-111">Ora della richiesta della sessione.</span><span class="sxs-lookup"><span data-stu-id="e6f92-111">Time of session request.</span></span> <span data-ttu-id="e6f92-112">Usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="e6f92-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e6f92-113">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e6f92-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6f92-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e6f92-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e6f92-115">int</span><span class="sxs-lookup"><span data-stu-id="e6f92-115">int</span></span></p></td>
<td><p><span data-ttu-id="e6f92-116">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="e6f92-116">ID number to identify the session.</span></span> <span data-ttu-id="e6f92-117">Usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="e6f92-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e6f92-118">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e6f92-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6f92-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="e6f92-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e6f92-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e6f92-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e6f92-121">URI per la conferenza.</span><span class="sxs-lookup"><span data-stu-id="e6f92-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6f92-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e6f92-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e6f92-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6f92-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6f92-124">Tipo di URI conferenza.</span><span class="sxs-lookup"><span data-stu-id="e6f92-124">Type of the conference URI.</span></span> <span data-ttu-id="e6f92-125">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e6f92-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6f92-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="e6f92-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e6f92-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="e6f92-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e6f92-128">Usato per le conferenze periodiche.</span><span class="sxs-lookup"><span data-stu-id="e6f92-128">Used for recurring conferences.</span></span> <span data-ttu-id="e6f92-129">Ogni istanza di una conferenza ricorrente ha lo stesso ConferenceUri ma un ConfInstance diverso.</span><span class="sxs-lookup"><span data-stu-id="e6f92-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6f92-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="e6f92-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e6f92-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6f92-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="e6f92-132">Ora di inizio per la conferenza.</span><span class="sxs-lookup"><span data-stu-id="e6f92-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6f92-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="e6f92-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e6f92-134">DateTime</span><span class="sxs-lookup"><span data-stu-id="e6f92-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="e6f92-135">Ora di fine per la conferenza.</span><span class="sxs-lookup"><span data-stu-id="e6f92-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6f92-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="e6f92-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e6f92-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e6f92-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e6f92-138">URI dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="e6f92-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6f92-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="e6f92-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="e6f92-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6f92-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6f92-141">Tipo di URI dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="e6f92-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="e6f92-142">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e6f92-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6f92-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e6f92-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e6f92-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6f92-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6f92-145">Tenant dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="e6f92-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="e6f92-146">Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e6f92-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6f92-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="e6f92-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e6f92-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6f92-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6f92-149">Nome di dominio completo del pool che ha ospitato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="e6f92-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6f92-150"><strong>Contrassegno</strong></span><span class="sxs-lookup"><span data-stu-id="e6f92-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="e6f92-151">smallint</span><span class="sxs-lookup"><span data-stu-id="e6f92-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="e6f92-152">Maschera di bit che contiene gli attributi della conferenza.</span><span class="sxs-lookup"><span data-stu-id="e6f92-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="e6f92-153">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="e6f92-153">Possible values are:</span></span></p>
<p><span data-ttu-id="e6f92-154">0X01-transazione sintetica</span><span class="sxs-lookup"><span data-stu-id="e6f92-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

