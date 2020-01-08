---
title: 'Lync Server 2013: Tabella ErrorCategory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9bd9cebf26a147b00873c17372eca77f0a11f2d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="fd6f1-102">Tabella ErrorCategory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd6f1-102">ErrorCategory table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd6f1-103">_**Argomento Ultima modifica:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="fd6f1-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="fd6f1-104">La tabella ErrorCategory contiene il nome descrittivo per ogni classificazione di diagnostica di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fd6f1-104">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="fd6f1-105">Per impostazione predefinita, Lync Server 2013 usa le classificazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd6f1-105">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="fd6f1-106">0--successo</span><span class="sxs-lookup"><span data-stu-id="fd6f1-106">0 -- Success</span></span>

  - <span data-ttu-id="fd6f1-107">1-errore previsto</span><span class="sxs-lookup"><span data-stu-id="fd6f1-107">1 -- Expected failure</span></span>

  - <span data-ttu-id="fd6f1-108">2-errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="fd6f1-108">2 – Unexpected failure</span></span>

<span data-ttu-id="fd6f1-109">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fd6f1-109">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd6f1-110">Colonna</span><span class="sxs-lookup"><span data-stu-id="fd6f1-110">Column</span></span></th>
<th><span data-ttu-id="fd6f1-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="fd6f1-111">Data Type</span></span></th>
<th><span data-ttu-id="fd6f1-112">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="fd6f1-112">Key/Index</span></span></th>
<th><span data-ttu-id="fd6f1-113">Dettagli</span><span class="sxs-lookup"><span data-stu-id="fd6f1-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd6f1-114"><strong>CategoryId</strong></span><span class="sxs-lookup"><span data-stu-id="fd6f1-114"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="fd6f1-115">tinyint</span><span class="sxs-lookup"><span data-stu-id="fd6f1-115">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fd6f1-116">Principale</span><span class="sxs-lookup"><span data-stu-id="fd6f1-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="fd6f1-117">Identificatore univoco per la classificazione.</span><span class="sxs-lookup"><span data-stu-id="fd6f1-117">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd6f1-118"><strong>Nome</strong></span><span class="sxs-lookup"><span data-stu-id="fd6f1-118"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="fd6f1-119">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fd6f1-119">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fd6f1-120">Valore e nome descrittivo assegnato alla classificazione.</span><span class="sxs-lookup"><span data-stu-id="fd6f1-120">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="fd6f1-121">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="fd6f1-121">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="fd6f1-122">0--successo</span><span class="sxs-lookup"><span data-stu-id="fd6f1-122">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="fd6f1-123">1-errore previsto</span><span class="sxs-lookup"><span data-stu-id="fd6f1-123">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="fd6f1-124">2-errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="fd6f1-124">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

