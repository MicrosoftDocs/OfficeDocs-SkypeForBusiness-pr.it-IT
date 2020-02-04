---
title: 'Lync Server 2013: tblLastChatId'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0fc42a3151b5863885fdb3853ea529503e18a6b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="e239d-102">tblLastChatId in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e239d-102">tblLastChatId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e239d-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e239d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e239d-104">tblLastChatId contiene l'ultimo ID chat generato (e usato nella tabella tblChat) per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="e239d-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="e239d-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="e239d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e239d-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="e239d-106">Column</span></span></th>
<th><span data-ttu-id="e239d-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="e239d-107">Type</span></span></th>
<th><span data-ttu-id="e239d-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e239d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e239d-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="e239d-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="e239d-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="e239d-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e239d-111">ID nodo (solo chat room-tipo).</span><span class="sxs-lookup"><span data-stu-id="e239d-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e239d-112">Dalla LastChatId</span><span class="sxs-lookup"><span data-stu-id="e239d-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="e239d-113">bigint e non null</span><span class="sxs-lookup"><span data-stu-id="e239d-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="e239d-114">Ultimo ID chat usato.</span><span class="sxs-lookup"><span data-stu-id="e239d-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="e239d-115">Tasti</span><span class="sxs-lookup"><span data-stu-id="e239d-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e239d-116">Colonna</span><span class="sxs-lookup"><span data-stu-id="e239d-116">Column</span></span></th>
<th><span data-ttu-id="e239d-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e239d-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e239d-118">&lt;nodeID, dalla LastChatId&gt;</span><span class="sxs-lookup"><span data-stu-id="e239d-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="e239d-119">Chiave primaria (solo nodeID è sufficiente per l'elaborazione).</span><span class="sxs-lookup"><span data-stu-id="e239d-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e239d-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="e239d-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="e239d-121">Chiave esterna con ricerca nella tabella tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="e239d-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="e239d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e239d-122">See Also</span></span>


[<span data-ttu-id="e239d-123">tblChat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e239d-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

