---
title: 'Lync Server 2013: tabella AppliedBandwidthSource'
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
ms.openlocfilehash: 6ffc7104024c3d4d8fd0aa409fa965d6a426cd34
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appliedbandwidthsource-table-in-lync-server-2013"></a><span data-ttu-id="b162e-102">Tabella AppliedBandwidthSource in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b162e-102">AppliedBandwidthSource table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b162e-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b162e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b162e-p101">La tabella AppliedBandwidthSource è una tabella di supporto. Ogni record rappresenta un'origine.</span><span class="sxs-lookup"><span data-stu-id="b162e-p101">The AppliedBandwidthSource table is a supporting table. Each record represents one source.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b162e-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="b162e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b162e-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="b162e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b162e-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="b162e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b162e-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="b162e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b162e-110"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="b162e-110"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b162e-111">int</span><span class="sxs-lookup"><span data-stu-id="b162e-111">int</span></span></p></td>
<td><p><span data-ttu-id="b162e-112">Principale</span><span class="sxs-lookup"><span data-stu-id="b162e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b162e-113">Numero univoco che identifica l'origine.</span><span class="sxs-lookup"><span data-stu-id="b162e-113">Unique number identifying the source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b162e-114"><strong>AppliedBandwidthSource</strong></span><span class="sxs-lookup"><span data-stu-id="b162e-114"><strong>AppliedBandwidthSource</strong></span></span></p></td>
<td><p><span data-ttu-id="b162e-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="b162e-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b162e-116">Univoco</span><span class="sxs-lookup"><span data-stu-id="b162e-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="b162e-p102">Origine del limite della larghezza di banda imposto. Descrive l'origine del limite della larghezza di banda, ad esempio "Policy Server", "TURN Server" o "Modality".</span><span class="sxs-lookup"><span data-stu-id="b162e-p102">This is the source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

