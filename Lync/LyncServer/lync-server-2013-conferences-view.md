---
title: 'Lync Server 2013: visualizzazione conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36278c1053c2b5737e0de6caf914c050db93ea4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="c5dd2-102">Visualizzazione conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5dd2-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5dd2-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c5dd2-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c5dd2-104">La visualizzazione conferenze archivia le informazioni sulle conferenze.</span><span class="sxs-lookup"><span data-stu-id="c5dd2-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="c5dd2-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c5dd2-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5dd2-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="c5dd2-106">Column</span></span></th>
<th><span data-ttu-id="c5dd2-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c5dd2-107">Data Type</span></span></th>
<th><span data-ttu-id="c5dd2-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c5dd2-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5dd2-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c5dd2-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dd2-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="c5dd2-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="c5dd2-111">Ora della richiesta della sessione.</span><span class="sxs-lookup"><span data-stu-id="c5dd2-111">Time of session request.</span></span> <span data-ttu-id="c5dd2-112">Usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="c5dd2-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="c5dd2-113">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c5dd2-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5dd2-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c5dd2-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dd2-115">int</span><span class="sxs-lookup"><span data-stu-id="c5dd2-115">int</span></span></p></td>
<td><p><span data-ttu-id="c5dd2-116">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="c5dd2-116">ID number to identify the session.</span></span> <span data-ttu-id="c5dd2-117">Usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="c5dd2-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="c5dd2-118">Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c5dd2-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5dd2-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="c5dd2-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dd2-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c5dd2-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c5dd2-121">URI per la conferenza.</span><span class="sxs-lookup"><span data-stu-id="c5dd2-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5dd2-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c5dd2-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dd2-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5dd2-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5dd2-124">Tipo di URI conferenza.</span><span class="sxs-lookup"><span data-stu-id="c5dd2-124">Type of the conference URI.</span></span> <span data-ttu-id="c5dd2-125">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c5dd2-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5dd2-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="c5dd2-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dd2-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="c5dd2-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c5dd2-128">Usato per le conferenze periodiche.</span><span class="sxs-lookup"><span data-stu-id="c5dd2-128">Used for recurring conferences.</span></span> <span data-ttu-id="c5dd2-129">Ogni istanza di una conferenza ricorrente ha lo stesso ConferenceUri ma un ConfInstance diverso.</span><span class="sxs-lookup"><span data-stu-id="c5dd2-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5dd2-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="c5dd2-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dd2-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="c5dd2-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="c5dd2-132">Ora di inizio per la conferenza.</span><span class="sxs-lookup"><span data-stu-id="c5dd2-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5dd2-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="c5dd2-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dd2-134">DateTime</span><span class="sxs-lookup"><span data-stu-id="c5dd2-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="c5dd2-135">Ora di fine per la conferenza.</span><span class="sxs-lookup"><span data-stu-id="c5dd2-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5dd2-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="c5dd2-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dd2-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c5dd2-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c5dd2-138">URI dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="c5dd2-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5dd2-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="c5dd2-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dd2-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5dd2-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5dd2-141">Tipo di URI dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="c5dd2-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="c5dd2-142">Per altre informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c5dd2-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5dd2-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="c5dd2-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dd2-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5dd2-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5dd2-145">Tenant dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="c5dd2-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="c5dd2-146">Per altre informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="c5dd2-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5dd2-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="c5dd2-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dd2-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c5dd2-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c5dd2-149">Nome di dominio completo del pool che ha ospitato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="c5dd2-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5dd2-150"><strong>Contrassegno</strong></span><span class="sxs-lookup"><span data-stu-id="c5dd2-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="c5dd2-151">smallint</span><span class="sxs-lookup"><span data-stu-id="c5dd2-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="c5dd2-152">Maschera di bit che contiene gli attributi della conferenza.</span><span class="sxs-lookup"><span data-stu-id="c5dd2-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="c5dd2-153">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="c5dd2-153">Possible values are:</span></span></p>
<p><span data-ttu-id="c5dd2-154">0X01-transazione sintetica</span><span class="sxs-lookup"><span data-stu-id="c5dd2-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

