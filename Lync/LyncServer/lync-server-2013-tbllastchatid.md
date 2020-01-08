---
title: 'Lync Server 2013: tblLastChatId'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bddc89952b544a71c469538cf11f65658e19e38d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="e8e6e-102">tblLastChatId in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8e6e-102">tblLastChatId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8e6e-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e8e6e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e8e6e-104">tblLastChatId contiene l'ultimo ID chat generato (e usato nella tabella tblChat) per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="e8e6e-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="e8e6e-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="e8e6e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8e6e-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="e8e6e-106">Column</span></span></th>
<th><span data-ttu-id="e8e6e-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="e8e6e-107">Type</span></span></th>
<th><span data-ttu-id="e8e6e-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8e6e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8e6e-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="e8e6e-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="e8e6e-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="e8e6e-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e8e6e-111">ID nodo (solo chat room-tipo).</span><span class="sxs-lookup"><span data-stu-id="e8e6e-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8e6e-112">Dalla LastChatId</span><span class="sxs-lookup"><span data-stu-id="e8e6e-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="e8e6e-113">bigint e non null</span><span class="sxs-lookup"><span data-stu-id="e8e6e-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="e8e6e-114">Ultimo ID chat usato.</span><span class="sxs-lookup"><span data-stu-id="e8e6e-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="e8e6e-115">Tasti</span><span class="sxs-lookup"><span data-stu-id="e8e6e-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8e6e-116">Colonna</span><span class="sxs-lookup"><span data-stu-id="e8e6e-116">Column</span></span></th>
<th><span data-ttu-id="e8e6e-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8e6e-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8e6e-118">&lt;nodeID, dalla LastChatId&gt;</span><span class="sxs-lookup"><span data-stu-id="e8e6e-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="e8e6e-119">Chiave primaria (solo nodeID è sufficiente per l'elaborazione).</span><span class="sxs-lookup"><span data-stu-id="e8e6e-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8e6e-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="e8e6e-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="e8e6e-121">Chiave esterna con ricerca nella tabella tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="e8e6e-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="e8e6e-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8e6e-122">See Also</span></span>


[<span data-ttu-id="e8e6e-123">tblChat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8e6e-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

