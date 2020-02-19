---
title: 'Lync Server 2013: tabella IMReportSummary'
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
ms.openlocfilehash: 619f502f3671d5f8bfe66af2b157a9729ab0e952
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="9d571-102">Tabella IMReportSummary in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d571-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d571-103">_**Ultimo argomento modificato:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="9d571-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="9d571-104">La tabella IMReportSummaryTable offre un rapporto complessivo sulle sessioni di messaggistica istantanea eseguite in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9d571-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="9d571-105">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9d571-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d571-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="9d571-106">Column</span></span></th>
<th><span data-ttu-id="9d571-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9d571-107">Data Type</span></span></th>
<th><span data-ttu-id="9d571-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="9d571-108">Key/Index</span></span></th>
<th><span data-ttu-id="9d571-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9d571-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d571-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="9d571-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9d571-111">datetime</span><span class="sxs-lookup"><span data-stu-id="9d571-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="9d571-112">Principale</span><span class="sxs-lookup"><span data-stu-id="9d571-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="9d571-113">Data e ora di inizio della sessione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="9d571-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d571-114"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="9d571-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="9d571-115">char (1)</span><span class="sxs-lookup"><span data-stu-id="9d571-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="9d571-116">Principale</span><span class="sxs-lookup"><span data-stu-id="9d571-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d571-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="9d571-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="9d571-118">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="9d571-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="9d571-119">Principale</span><span class="sxs-lookup"><span data-stu-id="9d571-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="9d571-120">Nome di dominio completo del pool che ospita la sessione.</span><span class="sxs-lookup"><span data-stu-id="9d571-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d571-121"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="9d571-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="9d571-122">int</span><span class="sxs-lookup"><span data-stu-id="9d571-122">int</span></span></p></td>
<td><p><span data-ttu-id="9d571-123">Principale</span><span class="sxs-lookup"><span data-stu-id="9d571-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="9d571-124">Priorità della chiamata, ad esempio urgente o non urgente.</span><span class="sxs-lookup"><span data-stu-id="9d571-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="9d571-125">Le informazioni sulla priorità sono archiviate nella <a href="lync-server-2013-callpriorities-table.md">Tabella CallPriorities in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9d571-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d571-126"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="9d571-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="9d571-127">bigint</span><span class="sxs-lookup"><span data-stu-id="9d571-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d571-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="9d571-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="9d571-129">bigint</span><span class="sxs-lookup"><span data-stu-id="9d571-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9d571-130">Numero totale di messaggi istantanei scambiati durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="9d571-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

