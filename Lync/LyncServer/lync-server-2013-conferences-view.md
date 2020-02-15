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
ms.openlocfilehash: 56f292a35f5e4f24ba5226e06a308e780ce5c687
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="ff861-102">Visualizzazione conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff861-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff861-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ff861-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ff861-104">La visualizzazione conferenze archivia le informazioni sulle conferenze.</span><span class="sxs-lookup"><span data-stu-id="ff861-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="ff861-105">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ff861-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff861-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="ff861-106">Column</span></span></th>
<th><span data-ttu-id="ff861-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="ff861-107">Data Type</span></span></th>
<th><span data-ttu-id="ff861-108">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ff861-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff861-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ff861-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ff861-110">datetime</span><span class="sxs-lookup"><span data-stu-id="ff861-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="ff861-111">Ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="ff861-111">Time of session request.</span></span> <span data-ttu-id="ff861-112">Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="ff861-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="ff861-113">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ff861-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff861-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ff861-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ff861-115">int</span><span class="sxs-lookup"><span data-stu-id="ff861-115">int</span></span></p></td>
<td><p><span data-ttu-id="ff861-116">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="ff861-116">ID number to identify the session.</span></span> <span data-ttu-id="ff861-117">Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="ff861-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="ff861-118">Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ff861-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff861-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="ff861-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ff861-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ff861-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ff861-121">URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="ff861-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff861-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ff861-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ff861-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ff861-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ff861-124">Tipo dell'URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="ff861-124">Type of the conference URI.</span></span> <span data-ttu-id="ff861-125">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ff861-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff861-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="ff861-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="ff861-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="ff861-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ff861-128">Utilizzato per le conferenze ricorrenti.</span><span class="sxs-lookup"><span data-stu-id="ff861-128">Used for recurring conferences.</span></span> <span data-ttu-id="ff861-129">Ogni istanza di una conferenza ricorrente ha lo stesso ConferenceUri ma una ConfInstance diversa.</span><span class="sxs-lookup"><span data-stu-id="ff861-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff861-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="ff861-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ff861-131">datetime</span><span class="sxs-lookup"><span data-stu-id="ff861-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="ff861-132">Ora di inizio della conferenza.</span><span class="sxs-lookup"><span data-stu-id="ff861-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff861-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="ff861-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ff861-134">datetime</span><span class="sxs-lookup"><span data-stu-id="ff861-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="ff861-135">Ora di fine della conferenza.</span><span class="sxs-lookup"><span data-stu-id="ff861-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff861-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="ff861-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ff861-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ff861-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ff861-138">URI dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="ff861-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff861-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="ff861-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="ff861-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ff861-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ff861-141">Tipo di URI dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="ff861-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="ff861-142">Per ulteriori informazioni, vedere la <a href="lync-server-2013-uritypes-table.md">tabella UriTypes in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ff861-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff861-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ff861-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ff861-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ff861-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ff861-145">Tenant dell'utente che ha organizzato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="ff861-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="ff861-146">Per ulteriori informazioni, vedere la <a href="lync-server-2013-tenants-table.md">tabella tenant in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ff861-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff861-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="ff861-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ff861-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ff861-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ff861-149">Nome di dominio completo del pool che ha ospitato la conferenza.</span><span class="sxs-lookup"><span data-stu-id="ff861-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff861-150"><strong>Bandiera</strong></span><span class="sxs-lookup"><span data-stu-id="ff861-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="ff861-151">smallint</span><span class="sxs-lookup"><span data-stu-id="ff861-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="ff861-152">Maschera di bit che contiene gli attributi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="ff861-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="ff861-153">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="ff861-153">Possible values are:</span></span></p>
<p><span data-ttu-id="ff861-154">0X01 – transazione sintetica</span><span class="sxs-lookup"><span data-stu-id="ff861-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

