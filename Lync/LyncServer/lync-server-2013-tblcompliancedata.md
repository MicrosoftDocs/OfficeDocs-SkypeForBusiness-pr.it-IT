---
title: 'Lync Server 2013: tblComplianceData'
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
ms.openlocfilehash: 03f5a65b11c610849c5b9d031f24d236dcbcf332
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="dee1d-102">tblComplianceData in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dee1d-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dee1d-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="dee1d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="dee1d-104">tblComplianceData contiene gli eventi di conformità ancora non elaborati dall'adattatore di conformità.</span><span class="sxs-lookup"><span data-stu-id="dee1d-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="dee1d-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="dee1d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dee1d-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="dee1d-106">Column</span></span></th>
<th><span data-ttu-id="dee1d-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="dee1d-107">Type</span></span></th>
<th><span data-ttu-id="dee1d-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dee1d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dee1d-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="dee1d-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="dee1d-110">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="dee1d-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="dee1d-111">ID evento.</span><span class="sxs-lookup"><span data-stu-id="dee1d-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dee1d-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="dee1d-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="dee1d-113">smalldatetime, not null</span><span class="sxs-lookup"><span data-stu-id="dee1d-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="dee1d-114">Data/ora di inserimento (può essere molto lontana nel futuro per cmplType=9, poiché in tal caso la voce è solo un segnaposto).</span><span class="sxs-lookup"><span data-stu-id="dee1d-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dee1d-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="dee1d-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="dee1d-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="dee1d-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="dee1d-117">Tipo di evento di conformità:</span><span class="sxs-lookup"><span data-stu-id="dee1d-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="dee1d-118">1: chat</span><span class="sxs-lookup"><span data-stu-id="dee1d-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="dee1d-119">2: dialogo della chat</span><span class="sxs-lookup"><span data-stu-id="dee1d-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="dee1d-120">3: download di file</span><span class="sxs-lookup"><span data-stu-id="dee1d-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="dee1d-121">4: caricamento di file</span><span class="sxs-lookup"><span data-stu-id="dee1d-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="dee1d-122">9: trasferimento file provvisorio</span><span class="sxs-lookup"><span data-stu-id="dee1d-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="dee1d-123">10: eliminazione della chat (con sostituzione)</span><span class="sxs-lookup"><span data-stu-id="dee1d-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="dee1d-124">11: eliminazione della chat</span><span class="sxs-lookup"><span data-stu-id="dee1d-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dee1d-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="dee1d-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="dee1d-126">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="dee1d-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="dee1d-127">Data e ora dell'evento.</span><span class="sxs-lookup"><span data-stu-id="dee1d-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dee1d-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="dee1d-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="dee1d-129">nvarchar (255), non null</span><span class="sxs-lookup"><span data-stu-id="dee1d-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="dee1d-130">URI (Uniform Resource Identifier) del canale.</span><span class="sxs-lookup"><span data-stu-id="dee1d-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dee1d-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="dee1d-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="dee1d-132">bigint</span><span class="sxs-lookup"><span data-stu-id="dee1d-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="dee1d-133">ID chat (corrispondente alla tabella tblChat.chatId).</span><span class="sxs-lookup"><span data-stu-id="dee1d-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dee1d-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="dee1d-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="dee1d-135">int, not null</span><span class="sxs-lookup"><span data-stu-id="dee1d-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="dee1d-136">ID entità di chi effettua l'invio (corrispondente alla tabella tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="dee1d-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dee1d-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="dee1d-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="dee1d-138">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="dee1d-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="dee1d-139">URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="dee1d-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dee1d-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="dee1d-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="dee1d-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="dee1d-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="dee1d-142">Messaggio (la codifica dipende da cmplType).</span><span class="sxs-lookup"><span data-stu-id="dee1d-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="dee1d-143">Chiave</span><span class="sxs-lookup"><span data-stu-id="dee1d-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dee1d-144">Colonna</span><span class="sxs-lookup"><span data-stu-id="dee1d-144">Column</span></span></th>
<th><span data-ttu-id="dee1d-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dee1d-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dee1d-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="dee1d-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="dee1d-147">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="dee1d-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

