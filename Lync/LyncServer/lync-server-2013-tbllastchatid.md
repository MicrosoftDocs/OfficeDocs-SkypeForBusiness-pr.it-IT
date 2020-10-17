---
title: 'Lync Server 2013: LastChatId'
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
ms.openlocfilehash: b184d863ff9d0404fbc05b90a88f7c203499262a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523823"
---
# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="77318-102">LastChatId in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77318-102">tblLastChatId in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77318-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="77318-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="77318-104">LastChatId contiene l'ultimo ID chat generato (e utilizzato nella tabella tblChat) per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="77318-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="77318-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="77318-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77318-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="77318-106">Column</span></span></th>
<th><span data-ttu-id="77318-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="77318-107">Type</span></span></th>
<th><span data-ttu-id="77318-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77318-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77318-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="77318-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="77318-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="77318-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="77318-111">ID nodo (solo di tipo chat).</span><span class="sxs-lookup"><span data-stu-id="77318-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77318-112">Dalla LastChatId</span><span class="sxs-lookup"><span data-stu-id="77318-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="77318-113">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="77318-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="77318-114">Ultimo ID chat utilizzato.</span><span class="sxs-lookup"><span data-stu-id="77318-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="77318-115">Chiavi</span><span class="sxs-lookup"><span data-stu-id="77318-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77318-116">Colonna</span><span class="sxs-lookup"><span data-stu-id="77318-116">Column</span></span></th>
<th><span data-ttu-id="77318-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77318-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77318-118">&lt;nodeID, dalla LastChatId&gt;</span><span class="sxs-lookup"><span data-stu-id="77318-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="77318-119">Chiave primaria (solo nodeID è sufficiente per l'elaborazione).</span><span class="sxs-lookup"><span data-stu-id="77318-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77318-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="77318-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="77318-121">Chiave esterna con ricerca nella tabella tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="77318-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="77318-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77318-122">See Also</span></span>


[<span data-ttu-id="77318-123">tblChat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77318-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

