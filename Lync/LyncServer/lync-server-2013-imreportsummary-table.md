---
title: 'Lync Server 2013: tabella IMReportSummary'
description: 'Lync Server 2013: tabella IMReportSummary.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfafa81d1605845b29a3627321fcbc0f72ca7ac7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547742"
---
# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="f1eda-103">Tabella IMReportSummary in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1eda-103">IMReportSummary table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1eda-104">_**Ultimo argomento modificato:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="f1eda-104">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="f1eda-105">La tabella IMReportSummaryTable offre un rapporto complessivo sulle sessioni di messaggistica istantanea eseguite in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f1eda-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="f1eda-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1eda-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1eda-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="f1eda-107">Column</span></span></th>
<th><span data-ttu-id="f1eda-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="f1eda-108">Data Type</span></span></th>
<th><span data-ttu-id="f1eda-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="f1eda-109">Key/Index</span></span></th>
<th><span data-ttu-id="f1eda-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f1eda-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1eda-111"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="f1eda-111"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f1eda-112">datetime</span><span class="sxs-lookup"><span data-stu-id="f1eda-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="f1eda-113">Principale</span><span class="sxs-lookup"><span data-stu-id="f1eda-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="f1eda-114">Data e ora di inizio della sessione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="f1eda-114">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1eda-115"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="f1eda-115"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="f1eda-116">char (1)</span><span class="sxs-lookup"><span data-stu-id="f1eda-116">char(1)</span></span></p></td>
<td><p><span data-ttu-id="f1eda-117">Principale</span><span class="sxs-lookup"><span data-stu-id="f1eda-117">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1eda-118"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="f1eda-118"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="f1eda-119">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="f1eda-119">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="f1eda-120">Principale</span><span class="sxs-lookup"><span data-stu-id="f1eda-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="f1eda-121">Nome di dominio completo del pool che ospita la sessione.</span><span class="sxs-lookup"><span data-stu-id="f1eda-121">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1eda-122"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="f1eda-122"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="f1eda-123">int</span><span class="sxs-lookup"><span data-stu-id="f1eda-123">int</span></span></p></td>
<td><p><span data-ttu-id="f1eda-124">Principale</span><span class="sxs-lookup"><span data-stu-id="f1eda-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="f1eda-125">Priorità della chiamata, ad esempio urgente o non urgente.</span><span class="sxs-lookup"><span data-stu-id="f1eda-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="f1eda-126">Le informazioni sulla priorità sono archiviate nella <a href="lync-server-2013-callpriorities-table.md">Tabella CallPriorities in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f1eda-126">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1eda-127"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="f1eda-127"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="f1eda-128">bigint</span><span class="sxs-lookup"><span data-stu-id="f1eda-128">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1eda-129"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="f1eda-129"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="f1eda-130">bigint</span><span class="sxs-lookup"><span data-stu-id="f1eda-130">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1eda-131">Numero totale di messaggi istantanei scambiati durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="f1eda-131">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

