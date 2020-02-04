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
ms.openlocfilehash: a7a6be73d31892b5a0d5a3a5b10ad136f92afbf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="c879a-102">Tabella IMReportSummary in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c879a-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c879a-103">_**Argomento Ultima modifica:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="c879a-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="c879a-104">IMReportSummaryTable fornisce un report globale sulle sessioni di messaggistica istantanea svolte in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c879a-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="c879a-105">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c879a-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c879a-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="c879a-106">Column</span></span></th>
<th><span data-ttu-id="c879a-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c879a-107">Data Type</span></span></th>
<th><span data-ttu-id="c879a-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="c879a-108">Key/Index</span></span></th>
<th><span data-ttu-id="c879a-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c879a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c879a-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="c879a-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c879a-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="c879a-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="c879a-112">Principale</span><span class="sxs-lookup"><span data-stu-id="c879a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="c879a-113">Data e ora di inizio della sessione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="c879a-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c879a-114"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="c879a-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="c879a-115">carattere (1)</span><span class="sxs-lookup"><span data-stu-id="c879a-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="c879a-116">Principale</span><span class="sxs-lookup"><span data-stu-id="c879a-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c879a-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="c879a-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="c879a-118">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="c879a-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="c879a-119">Principale</span><span class="sxs-lookup"><span data-stu-id="c879a-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="c879a-120">Nome di dominio completo del pool che ospita la sessione.</span><span class="sxs-lookup"><span data-stu-id="c879a-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c879a-121"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="c879a-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="c879a-122">int</span><span class="sxs-lookup"><span data-stu-id="c879a-122">int</span></span></p></td>
<td><p><span data-ttu-id="c879a-123">Principale</span><span class="sxs-lookup"><span data-stu-id="c879a-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="c879a-124">Priorità, ad esempio urgente o non urgente, della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c879a-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="c879a-125">Le informazioni prioritarie sono archiviate nella <a href="lync-server-2013-callpriorities-table.md">Tabella CallPriorities in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="c879a-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c879a-126"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="c879a-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="c879a-127">bigint</span><span class="sxs-lookup"><span data-stu-id="c879a-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c879a-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="c879a-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="c879a-129">bigint</span><span class="sxs-lookup"><span data-stu-id="c879a-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c879a-130">Numero totale di messaggi istantanei scambiati durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="c879a-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

