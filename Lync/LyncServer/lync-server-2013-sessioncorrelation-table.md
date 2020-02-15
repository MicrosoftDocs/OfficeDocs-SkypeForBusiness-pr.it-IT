---
title: 'Lync Server 2013: tabella SessionCorrelation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionCorrelation table
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398091(v=OCS.15)
ms:contentKeyID: 48183267
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9551cf5824d5f13f6167f2aaeb301ab619f6209b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="4b3f0-102">Tabella SessionCorrelation in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b3f0-102">SessionCorrelation table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b3f0-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="4b3f0-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4b3f0-104">La tabella SessionCorrelation è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="4b3f0-104">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="4b3f0-105">Ogni record rappresenta un valore CorrelationID che viene utilizzato per correlare più sessioni.</span><span class="sxs-lookup"><span data-stu-id="4b3f0-105">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b3f0-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="4b3f0-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4b3f0-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="4b3f0-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4b3f0-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="4b3f0-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4b3f0-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="4b3f0-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b3f0-110"><strong>Checksum</strong></span><span class="sxs-lookup"><span data-stu-id="4b3f0-110"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="4b3f0-111">int</span><span class="sxs-lookup"><span data-stu-id="4b3f0-111">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b3f0-112"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="4b3f0-112"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="4b3f0-113">int</span><span class="sxs-lookup"><span data-stu-id="4b3f0-113">int</span></span></p></td>
<td><p><span data-ttu-id="4b3f0-114">Principale</span><span class="sxs-lookup"><span data-stu-id="4b3f0-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="4b3f0-115">Numero univoco che identifica l'A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="4b3f0-115">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b3f0-116"><strong>CorrelationID</strong></span><span class="sxs-lookup"><span data-stu-id="4b3f0-116"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="4b3f0-117">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4b3f0-117">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4b3f0-118">Univoco</span><span class="sxs-lookup"><span data-stu-id="4b3f0-118">Unique</span></span></p></td>
<td><p><span data-ttu-id="4b3f0-119">Le sessioni correlate avranno lo stesso ID correlazione.</span><span class="sxs-lookup"><span data-stu-id="4b3f0-119">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b3f0-120"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="4b3f0-120"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="4b3f0-121">datetime</span><span class="sxs-lookup"><span data-stu-id="4b3f0-121">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4b3f0-122">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="4b3f0-122">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

