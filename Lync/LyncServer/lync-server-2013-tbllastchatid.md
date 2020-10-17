---
title: 'Lync Server 2013: LastChatId'
description: 'Lync Server 2013: LastChatId.'
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
ms.openlocfilehash: 69e80a735e70c8a03441038f5e58eb93e0af1f82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547602"
---
# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="a470d-103">LastChatId in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a470d-103">tblLastChatId in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a470d-104">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="a470d-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="a470d-105">LastChatId contiene l'ultimo ID chat generato (e utilizzato nella tabella tblChat) per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="a470d-105">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="a470d-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="a470d-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a470d-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="a470d-107">Column</span></span></th>
<th><span data-ttu-id="a470d-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="a470d-108">Type</span></span></th>
<th><span data-ttu-id="a470d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a470d-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a470d-110">nodeID</span><span class="sxs-lookup"><span data-stu-id="a470d-110">nodeID</span></span></p></td>
<td><p><span data-ttu-id="a470d-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="a470d-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a470d-112">ID nodo (solo di tipo chat).</span><span class="sxs-lookup"><span data-stu-id="a470d-112">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a470d-113">Dalla LastChatId</span><span class="sxs-lookup"><span data-stu-id="a470d-113">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="a470d-114">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="a470d-114">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="a470d-115">Ultimo ID chat utilizzato.</span><span class="sxs-lookup"><span data-stu-id="a470d-115">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="a470d-116">Chiavi</span><span class="sxs-lookup"><span data-stu-id="a470d-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a470d-117">Colonna</span><span class="sxs-lookup"><span data-stu-id="a470d-117">Column</span></span></th>
<th><span data-ttu-id="a470d-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a470d-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a470d-119">&lt;nodeID, dalla LastChatId&gt;</span><span class="sxs-lookup"><span data-stu-id="a470d-119">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="a470d-120">Chiave primaria (solo nodeID è sufficiente per l'elaborazione).</span><span class="sxs-lookup"><span data-stu-id="a470d-120">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a470d-121">nodeID</span><span class="sxs-lookup"><span data-stu-id="a470d-121">nodeID</span></span></p></td>
<td><p><span data-ttu-id="a470d-122">Chiave esterna con ricerca nella tabella tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="a470d-122">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="a470d-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a470d-123">See Also</span></span>


[<span data-ttu-id="a470d-124">tblChat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a470d-124">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

