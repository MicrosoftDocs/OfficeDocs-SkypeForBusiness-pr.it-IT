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
ms.openlocfilehash: 48516f307a084d30fde06a03548119e0ada34d6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="42057-102">tblComplianceData in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42057-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42057-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="42057-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="42057-104">tblComplianceData contiene gli eventi di conformità che non sono stati ancora elaborati dalla scheda conformità.</span><span class="sxs-lookup"><span data-stu-id="42057-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="42057-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="42057-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42057-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="42057-106">Column</span></span></th>
<th><span data-ttu-id="42057-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="42057-107">Type</span></span></th>
<th><span data-ttu-id="42057-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42057-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42057-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="42057-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="42057-110">bigint e non null</span><span class="sxs-lookup"><span data-stu-id="42057-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="42057-111">ID evento.</span><span class="sxs-lookup"><span data-stu-id="42057-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42057-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="42057-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="42057-113">smalldatetime, not null</span><span class="sxs-lookup"><span data-stu-id="42057-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="42057-114">Ora di inserimento (può essere lontano in futuro per cmplType = 9 perché la voce è solo un segnaposto in questo caso).</span><span class="sxs-lookup"><span data-stu-id="42057-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42057-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="42057-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="42057-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="42057-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="42057-117">Tipo di evento di conformità:</span><span class="sxs-lookup"><span data-stu-id="42057-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="42057-118">1: chat</span><span class="sxs-lookup"><span data-stu-id="42057-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="42057-119">2: backchat</span><span class="sxs-lookup"><span data-stu-id="42057-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="42057-120">3: download di file</span><span class="sxs-lookup"><span data-stu-id="42057-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="42057-121">4: caricamento di file</span><span class="sxs-lookup"><span data-stu-id="42057-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="42057-122">9: trasferimento di file provvisorio</span><span class="sxs-lookup"><span data-stu-id="42057-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="42057-123">10: eliminazione della chat (con Sostituisci)</span><span class="sxs-lookup"><span data-stu-id="42057-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="42057-124">11: eliminazione chat</span><span class="sxs-lookup"><span data-stu-id="42057-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42057-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="42057-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="42057-126">bigint e non null</span><span class="sxs-lookup"><span data-stu-id="42057-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="42057-127">Indicatore di data e ora per l'evento.</span><span class="sxs-lookup"><span data-stu-id="42057-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42057-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="42057-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="42057-129">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="42057-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="42057-130">URI (Uniform Resource Identifier) del canale.</span><span class="sxs-lookup"><span data-stu-id="42057-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42057-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="42057-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="42057-132">bigint</span><span class="sxs-lookup"><span data-stu-id="42057-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="42057-133">ID chat (corrispondente alla tabella tblChat. chatId).</span><span class="sxs-lookup"><span data-stu-id="42057-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42057-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="42057-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="42057-135">int, not null</span><span class="sxs-lookup"><span data-stu-id="42057-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="42057-136">ID principale del poster (corrispondente alla tabella tblPrincipal. prinID).</span><span class="sxs-lookup"><span data-stu-id="42057-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42057-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="42057-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="42057-138">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="42057-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="42057-139">URI utente.</span><span class="sxs-lookup"><span data-stu-id="42057-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42057-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="42057-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="42057-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="42057-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="42057-142">Messaggio (la codifica dipende da cmplType).</span><span class="sxs-lookup"><span data-stu-id="42057-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="42057-143">Chiave</span><span class="sxs-lookup"><span data-stu-id="42057-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42057-144">Colonna</span><span class="sxs-lookup"><span data-stu-id="42057-144">Column</span></span></th>
<th><span data-ttu-id="42057-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42057-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42057-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="42057-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="42057-147">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="42057-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

