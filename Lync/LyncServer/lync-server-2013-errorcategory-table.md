---
title: 'Lync Server 2013: Tabella ErrorCategory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f21535c1806223e7687ceb24ee94a93fe15238d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533153"
---
# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="82790-102">Tabella ErrorCategory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82790-102">ErrorCategory table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82790-103">_**Ultimo argomento modificato:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="82790-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="82790-104">La tabella ErrorCategory contiene il nome descrittivo per ogni classificazione diagnostica di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="82790-104">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="82790-105">Per impostazione predefinita, Lync Server 2013 utilizza le classificazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="82790-105">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="82790-106">0 -- Esito positivo</span><span class="sxs-lookup"><span data-stu-id="82790-106">0 -- Success</span></span>

  - <span data-ttu-id="82790-107">1--errore previsto</span><span class="sxs-lookup"><span data-stu-id="82790-107">1 -- Expected failure</span></span>

  - <span data-ttu-id="82790-108">2 -- Errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="82790-108">2 – Unexpected failure</span></span>

<span data-ttu-id="82790-109">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="82790-109">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82790-110">Colonna</span><span class="sxs-lookup"><span data-stu-id="82790-110">Column</span></span></th>
<th><span data-ttu-id="82790-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="82790-111">Data Type</span></span></th>
<th><span data-ttu-id="82790-112">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="82790-112">Key/Index</span></span></th>
<th><span data-ttu-id="82790-113">Dettagli</span><span class="sxs-lookup"><span data-stu-id="82790-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82790-114"><strong>CategoryId</strong></span><span class="sxs-lookup"><span data-stu-id="82790-114"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="82790-115">tinyint</span><span class="sxs-lookup"><span data-stu-id="82790-115">tinyint</span></span></p></td>
<td><p><span data-ttu-id="82790-116">Principale</span><span class="sxs-lookup"><span data-stu-id="82790-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="82790-117">Identificatore univoco della classificazione.</span><span class="sxs-lookup"><span data-stu-id="82790-117">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82790-118"><strong>Nome</strong></span><span class="sxs-lookup"><span data-stu-id="82790-118"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="82790-119">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="82790-119">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="82790-p102">Valore e nome descrittivo assegnati alla classificazione. I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="82790-p102">Value and friendly name assigned to the classification. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="82790-122">0 -- Esito positivo</span><span class="sxs-lookup"><span data-stu-id="82790-122">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="82790-123">1--errore previsto</span><span class="sxs-lookup"><span data-stu-id="82790-123">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="82790-124">2 -- Errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="82790-124">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

