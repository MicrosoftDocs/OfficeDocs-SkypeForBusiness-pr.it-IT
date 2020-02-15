---
title: 'Lync Server 2013: tabella conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 733b3fc6fa77f8f18de1a5c79be86a5aea340cec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="f3c2c-102">Tabella conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3c2c-102">Conference table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3c2c-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f3c2c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f3c2c-p101">La tabella Conference è una tabella di supporto. Ogni record rappresenta una sessione di conferenza o peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="f3c2c-p101">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f3c2c-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="f3c2c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f3c2c-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="f3c2c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f3c2c-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="f3c2c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f3c2c-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="f3c2c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f3c2c-110"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="f3c2c-110"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f3c2c-111">int</span><span class="sxs-lookup"><span data-stu-id="f3c2c-111">int</span></span></p></td>
<td><p><span data-ttu-id="f3c2c-112">Principale</span><span class="sxs-lookup"><span data-stu-id="f3c2c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f3c2c-113">Numero univoco che identifica il record della conferenza.</span><span class="sxs-lookup"><span data-stu-id="f3c2c-113">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3c2c-114"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="f3c2c-114"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="f3c2c-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f3c2c-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f3c2c-116">univoco</span><span class="sxs-lookup"><span data-stu-id="f3c2c-116">unique</span></span></p></td>
<td><p><span data-ttu-id="f3c2c-117">URI conferenza nel caso di una conferenza oppure DialogID nel caso di una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="f3c2c-117">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f3c2c-118"><strong>Checksum</strong></span><span class="sxs-lookup"><span data-stu-id="f3c2c-118"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="f3c2c-119">int</span><span class="sxs-lookup"><span data-stu-id="f3c2c-119">int</span></span></p></td>
<td><p><span data-ttu-id="f3c2c-120">Indice</span><span class="sxs-lookup"><span data-stu-id="f3c2c-120">index</span></span></p></td>
<td><p><span data-ttu-id="f3c2c-p102">Checksum dell'URI conferenza. Per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f3c2c-p102">Checksum of the conference URI. This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f3c2c-123"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="f3c2c-123"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="f3c2c-124">datetime</span><span class="sxs-lookup"><span data-stu-id="f3c2c-124">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f3c2c-125">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="f3c2c-125">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

