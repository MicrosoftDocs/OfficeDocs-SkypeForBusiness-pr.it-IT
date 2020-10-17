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
ms.openlocfilehash: 162676768c3cb358db436dc2ba40ce378a31ba6c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509453"
---
# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="6dade-102">tblComplianceData in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dade-102">tblComplianceData in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6dade-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="6dade-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="6dade-104">tblComplianceData contiene gli eventi di conformità ancora non elaborati dall'adattatore di conformità.</span><span class="sxs-lookup"><span data-stu-id="6dade-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="6dade-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="6dade-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6dade-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="6dade-106">Column</span></span></th>
<th><span data-ttu-id="6dade-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="6dade-107">Type</span></span></th>
<th><span data-ttu-id="6dade-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6dade-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6dade-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="6dade-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="6dade-110">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="6dade-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="6dade-111">ID evento.</span><span class="sxs-lookup"><span data-stu-id="6dade-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dade-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="6dade-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="6dade-113">smalldatetime, not null</span><span class="sxs-lookup"><span data-stu-id="6dade-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="6dade-114">Data/ora di inserimento (può essere molto lontana nel futuro per cmplType=9, poiché in tal caso la voce è solo un segnaposto).</span><span class="sxs-lookup"><span data-stu-id="6dade-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6dade-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="6dade-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="6dade-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="6dade-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6dade-117">Tipo di evento di conformità:</span><span class="sxs-lookup"><span data-stu-id="6dade-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="6dade-118">1: chat</span><span class="sxs-lookup"><span data-stu-id="6dade-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="6dade-119">2: dialogo della chat</span><span class="sxs-lookup"><span data-stu-id="6dade-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="6dade-120">3: download di file</span><span class="sxs-lookup"><span data-stu-id="6dade-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="6dade-121">4: caricamento di file</span><span class="sxs-lookup"><span data-stu-id="6dade-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="6dade-122">9: trasferimento file provvisorio</span><span class="sxs-lookup"><span data-stu-id="6dade-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="6dade-123">10: eliminazione della chat (con sostituzione)</span><span class="sxs-lookup"><span data-stu-id="6dade-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="6dade-124">11: eliminazione della chat</span><span class="sxs-lookup"><span data-stu-id="6dade-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dade-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="6dade-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="6dade-126">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="6dade-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="6dade-127">Data e ora dell'evento.</span><span class="sxs-lookup"><span data-stu-id="6dade-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6dade-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="6dade-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="6dade-129">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="6dade-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="6dade-130">URI (Uniform Resource Identifier) del canale.</span><span class="sxs-lookup"><span data-stu-id="6dade-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dade-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="6dade-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="6dade-132">bigint</span><span class="sxs-lookup"><span data-stu-id="6dade-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="6dade-133">ID chat (corrispondente alla tabella tblChat.chatId).</span><span class="sxs-lookup"><span data-stu-id="6dade-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6dade-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="6dade-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="6dade-135">int, not null</span><span class="sxs-lookup"><span data-stu-id="6dade-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6dade-136">ID entità di chi effettua l'invio (corrispondente alla tabella tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="6dade-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dade-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="6dade-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="6dade-138">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="6dade-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="6dade-139">URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6dade-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6dade-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="6dade-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="6dade-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="6dade-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="6dade-142">Messaggio (la codifica dipende da cmplType).</span><span class="sxs-lookup"><span data-stu-id="6dade-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="6dade-143">Chiave</span><span class="sxs-lookup"><span data-stu-id="6dade-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6dade-144">Colonna</span><span class="sxs-lookup"><span data-stu-id="6dade-144">Column</span></span></th>
<th><span data-ttu-id="6dade-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6dade-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6dade-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="6dade-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="6dade-147">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="6dade-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

