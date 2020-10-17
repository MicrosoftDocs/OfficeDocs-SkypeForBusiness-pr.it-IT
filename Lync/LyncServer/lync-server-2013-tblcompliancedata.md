---
title: 'Lync Server 2013: tblComplianceData'
description: 'Lync Server 2013: tblComplianceData.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c597d67054303de2753182b37419f68051d3af8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568102"
---
# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="fda0d-103">tblComplianceData in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fda0d-103">tblComplianceData in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fda0d-104">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="fda0d-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="fda0d-105">tblComplianceData contiene gli eventi di conformità ancora non elaborati dall'adattatore di conformità.</span><span class="sxs-lookup"><span data-stu-id="fda0d-105">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="fda0d-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="fda0d-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fda0d-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="fda0d-107">Column</span></span></th>
<th><span data-ttu-id="fda0d-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="fda0d-108">Type</span></span></th>
<th><span data-ttu-id="fda0d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fda0d-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fda0d-110">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="fda0d-110">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="fda0d-111">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="fda0d-111">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="fda0d-112">ID evento.</span><span class="sxs-lookup"><span data-stu-id="fda0d-112">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fda0d-113">entryDate</span><span class="sxs-lookup"><span data-stu-id="fda0d-113">entryDate</span></span></p></td>
<td><p><span data-ttu-id="fda0d-114">smalldatetime, not null</span><span class="sxs-lookup"><span data-stu-id="fda0d-114">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="fda0d-115">Data/ora di inserimento (può essere molto lontana nel futuro per cmplType=9, poiché in tal caso la voce è solo un segnaposto).</span><span class="sxs-lookup"><span data-stu-id="fda0d-115">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fda0d-116">cmplType</span><span class="sxs-lookup"><span data-stu-id="fda0d-116">cmplType</span></span></p></td>
<td><p><span data-ttu-id="fda0d-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="fda0d-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fda0d-118">Tipo di evento di conformità:</span><span class="sxs-lookup"><span data-stu-id="fda0d-118">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="fda0d-119">1: chat</span><span class="sxs-lookup"><span data-stu-id="fda0d-119">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="fda0d-120">2: dialogo della chat</span><span class="sxs-lookup"><span data-stu-id="fda0d-120">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="fda0d-121">3: download di file</span><span class="sxs-lookup"><span data-stu-id="fda0d-121">3: File download</span></span></p></li>
<li><p><span data-ttu-id="fda0d-122">4: caricamento di file</span><span class="sxs-lookup"><span data-stu-id="fda0d-122">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="fda0d-123">9: trasferimento file provvisorio</span><span class="sxs-lookup"><span data-stu-id="fda0d-123">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="fda0d-124">10: eliminazione della chat (con sostituzione)</span><span class="sxs-lookup"><span data-stu-id="fda0d-124">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="fda0d-125">11: eliminazione della chat</span><span class="sxs-lookup"><span data-stu-id="fda0d-125">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fda0d-126">cmplTime</span><span class="sxs-lookup"><span data-stu-id="fda0d-126">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="fda0d-127">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="fda0d-127">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="fda0d-128">Data e ora dell'evento.</span><span class="sxs-lookup"><span data-stu-id="fda0d-128">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fda0d-129">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="fda0d-129">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="fda0d-130">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="fda0d-130">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="fda0d-131">URI (Uniform Resource Identifier) del canale.</span><span class="sxs-lookup"><span data-stu-id="fda0d-131">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fda0d-132">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="fda0d-132">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="fda0d-133">bigint</span><span class="sxs-lookup"><span data-stu-id="fda0d-133">bigint</span></span></p></td>
<td><p><span data-ttu-id="fda0d-134">ID chat (corrispondente alla tabella tblChat.chatId).</span><span class="sxs-lookup"><span data-stu-id="fda0d-134">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fda0d-135">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="fda0d-135">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="fda0d-136">int, not null</span><span class="sxs-lookup"><span data-stu-id="fda0d-136">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fda0d-137">ID entità di chi effettua l'invio (corrispondente alla tabella tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="fda0d-137">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fda0d-138">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="fda0d-138">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="fda0d-139">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="fda0d-139">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="fda0d-140">URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fda0d-140">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fda0d-141">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="fda0d-141">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="fda0d-142">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="fda0d-142">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="fda0d-143">Messaggio (la codifica dipende da cmplType).</span><span class="sxs-lookup"><span data-stu-id="fda0d-143">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="fda0d-144">Chiave</span><span class="sxs-lookup"><span data-stu-id="fda0d-144">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fda0d-145">Colonna</span><span class="sxs-lookup"><span data-stu-id="fda0d-145">Column</span></span></th>
<th><span data-ttu-id="fda0d-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fda0d-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fda0d-147">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="fda0d-147">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="fda0d-148">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="fda0d-148">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

