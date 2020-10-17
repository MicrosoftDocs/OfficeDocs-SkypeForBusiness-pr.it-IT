---
title: 'Lync Server 2013: visualizzazione conferenze'
description: 'Lync Server 2013: visualizzazione conferenze.'
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
ms.openlocfilehash: dee7fbb7c839c351fc9c81716a5800a678980549
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561582"
---
# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="bb572-103">Visualizzazione conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb572-103">Conferences view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb572-104">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="bb572-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="bb572-105">La visualizzazione conferenze archivia le informazioni sulle conferenze.</span><span class="sxs-lookup"><span data-stu-id="bb572-105">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="bb572-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bb572-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb572-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="bb572-107">Column</span></span></th>
<th><span data-ttu-id="bb572-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="bb572-108">Data Type</span></span></th>
<th><span data-ttu-id="bb572-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="bb572-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb572-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="bb572-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bb572-111">datetime</span><span class="sxs-lookup"><span data-stu-id="bb572-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="bb572-112">Ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="bb572-112">Time of session request.</span></span> <span data-ttu-id="bb572-113">Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="bb572-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="bb572-114">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bb572-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb572-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="bb572-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bb572-116">int</span><span class="sxs-lookup"><span data-stu-id="bb572-116">int</span></span></p></td>
<td><p><span data-ttu-id="bb572-117">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="bb572-117">ID number to identify the session.</span></span> <span data-ttu-id="bb572-118">Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="bb572-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="bb572-119">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bb572-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb572-120"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="bb572-120"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="bb572-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="bb572-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="bb572-122">URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="bb572-122">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb572-123"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="bb572-123"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="bb572-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bb572-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bb572-125">Tipo dell'URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="bb572-125">Type of the conference URI.</span></span> <span data-ttu-id="bb572-126">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bb572-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb572-127"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="bb572-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="bb572-128">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="bb572-128">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="bb572-129">Utilizzato per le conferenze ricorrenti.</span><span class="sxs-lookup"><span data-stu-id="bb572-129">Used for recurring conferences.</span></span> <span data-ttu-id="bb572-130">Ogni istanza di una conferenza ricorrente ha lo stesso ConferenceUri ma una ConfInstance diversa.</span><span class="sxs-lookup"><span data-stu-id="bb572-130">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb572-131"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="bb572-131"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bb572-132">datetime</span><span class="sxs-lookup"><span data-stu-id="bb572-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="bb572-133">Ora di inizio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="bb572-133">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb572-134"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="bb572-134"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bb572-135">datetime</span><span class="sxs-lookup"><span data-stu-id="bb572-135">datetime</span></span></p></td>
<td><p><span data-ttu-id="bb572-136">Ora di fine della conferenza.</span><span class="sxs-lookup"><span data-stu-id="bb572-136">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb572-137"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="bb572-137"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="bb572-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="bb572-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="bb572-139">URI dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="bb572-139">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb572-140"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="bb572-140"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="bb572-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bb572-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bb572-142">Tipo di URI dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="bb572-142">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="bb572-143">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bb572-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb572-144"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="bb572-144"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="bb572-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bb572-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bb572-146">Tenant dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="bb572-146">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="bb572-147">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bb572-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb572-148"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="bb572-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="bb572-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bb572-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bb572-150">Nome di dominio completo del pool che ha ospitato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="bb572-150">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb572-151"><strong>Bandiera</strong></span><span class="sxs-lookup"><span data-stu-id="bb572-151"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="bb572-152">smallint</span><span class="sxs-lookup"><span data-stu-id="bb572-152">smallint</span></span></p></td>
<td><p><span data-ttu-id="bb572-153">Maschera di bit che contiene gli attributi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="bb572-153">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="bb572-154">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="bb572-154">Possible values are:</span></span></p>
<p><span data-ttu-id="bb572-155">0X01 – transazione sintetica</span><span class="sxs-lookup"><span data-stu-id="bb572-155">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

