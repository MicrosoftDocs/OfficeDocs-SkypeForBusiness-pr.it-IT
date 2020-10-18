---
title: 'Lync Server 2013: tabella AppliedBandwidthSource'
description: 'Lync Server 2013: tabella AppliedBandwidthSource.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppliedBandwidthSource table
ms:assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425725(v=OCS.15)
ms:contentKeyID: 48183638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc22d3a978a99cb13317e2a32fdb65382ce106c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573502"
---
# <a name="appliedbandwidthsource-table-in-lync-server-2013"></a><span data-ttu-id="9a740-103">Tabella AppliedBandwidthSource in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a740-103">AppliedBandwidthSource table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a740-104">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="9a740-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="9a740-p101">La tabella AppliedBandwidthSource è una tabella di supporto. Ogni record rappresenta un'origine.</span><span class="sxs-lookup"><span data-stu-id="9a740-p101">The AppliedBandwidthSource table is a supporting table. Each record represents one source.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a740-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="9a740-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9a740-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="9a740-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9a740-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="9a740-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9a740-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="9a740-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a740-111"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="9a740-111"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="9a740-112">int</span><span class="sxs-lookup"><span data-stu-id="9a740-112">int</span></span></p></td>
<td><p><span data-ttu-id="9a740-113">Principale</span><span class="sxs-lookup"><span data-stu-id="9a740-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="9a740-114">Numero univoco che identifica l'origine.</span><span class="sxs-lookup"><span data-stu-id="9a740-114">Unique number identifying the source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a740-115"><strong>AppliedBandwidthSource</strong></span><span class="sxs-lookup"><span data-stu-id="9a740-115"><strong>AppliedBandwidthSource</strong></span></span></p></td>
<td><p><span data-ttu-id="9a740-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="9a740-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9a740-117">Univoco</span><span class="sxs-lookup"><span data-stu-id="9a740-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="9a740-p102">Origine del limite della larghezza di banda imposto. Descrive l'origine del limite della larghezza di banda, ad esempio "Policy Server", "TURN Server" o "Modality".</span><span class="sxs-lookup"><span data-stu-id="9a740-p102">This is the source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

