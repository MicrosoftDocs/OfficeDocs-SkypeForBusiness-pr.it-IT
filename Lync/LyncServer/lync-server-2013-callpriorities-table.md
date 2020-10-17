---
title: 'Lync Server 2013: Tabella CallPriorities'
description: 'Lync Server 2013: Tabella CallPriorities.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallPriorities table
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398093(v=OCS.15)
ms:contentKeyID: 48183275
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3cd1639921c63630e157744dbc8af22c50fac7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565182"
---
# <a name="callpriorities-table-in-lync-server-2013"></a><span data-ttu-id="eed74-103">Tabella CallPriorities in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eed74-103">CallPriorities table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eed74-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="eed74-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="eed74-105">La tabella CallPriorities è una tabella statica in cui è archiviato l'elenco delle possibili priorità delle chiamate, ad esempio 'emergency' (di emergenza), 'urgent' (urgente) o 'normal' (normale).</span><span class="sxs-lookup"><span data-stu-id="eed74-105">The CallPriorities table is a static table that stores the list of possible call priorities, such as ‘emergency’, ‘urgent’, or ‘normal’.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eed74-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="eed74-106">Column</span></span></th>
<th><span data-ttu-id="eed74-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="eed74-107">Data Type</span></span></th>
<th><span data-ttu-id="eed74-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="eed74-108">Key/Index</span></span></th>
<th><span data-ttu-id="eed74-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="eed74-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eed74-110"><strong>PriorityId</strong></span><span class="sxs-lookup"><span data-stu-id="eed74-110"><strong>PriorityId</strong></span></span></p></td>
<td><p><span data-ttu-id="eed74-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="eed74-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="eed74-112">Principale</span><span class="sxs-lookup"><span data-stu-id="eed74-112">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eed74-113"><strong>Priorità </strong></span><span class="sxs-lookup"><span data-stu-id="eed74-113"><strong>Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="eed74-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="eed74-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eed74-115">Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="eed74-115">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="eed74-116">0 - Sconosciuto</span><span class="sxs-lookup"><span data-stu-id="eed74-116">0 - Unknown</span></span></p></li>
<li><p><span data-ttu-id="eed74-117">1 - Non urgente</span><span class="sxs-lookup"><span data-stu-id="eed74-117">1 – Non-Urgent</span></span></p></li>
<li><p><span data-ttu-id="eed74-118">2 - Normale</span><span class="sxs-lookup"><span data-stu-id="eed74-118">2 - Normal</span></span></p></li>
<li><p><span data-ttu-id="eed74-119">3 - Urgente</span><span class="sxs-lookup"><span data-stu-id="eed74-119">3 - Urgent</span></span></p></li>
<li><p><span data-ttu-id="eed74-120">4 - Emergenza</span><span class="sxs-lookup"><span data-stu-id="eed74-120">4 - Emergency</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

