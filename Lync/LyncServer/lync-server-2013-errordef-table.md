---
title: 'Lync Server 2013: tabella ErrorDef'
description: 'Lync Server 2013: tabella ErrorDef.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorDef table
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398503(v=OCS.15)
ms:contentKeyID: 48184403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58980a671b54007012bbbf6780e24c162aebe00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542752"
---
# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="eccb4-103">Tabella ErrorDef in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eccb4-103">ErrorDef table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eccb4-104">_**Ultimo argomento modificato:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="eccb4-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="eccb4-105">Nella tabella ErrorDef vengono archiviate informazioni su ogni tipo di errore che può verificarsi.</span><span class="sxs-lookup"><span data-stu-id="eccb4-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="eccb4-106">Ogni record è un tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="eccb4-106">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eccb4-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="eccb4-107">Column</span></span></th>
<th><span data-ttu-id="eccb4-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="eccb4-108">Data Type</span></span></th>
<th><span data-ttu-id="eccb4-109">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="eccb4-109">Key/Index</span></span></th>
<th><span data-ttu-id="eccb4-110">Dettagli</span><span class="sxs-lookup"><span data-stu-id="eccb4-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eccb4-111"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="eccb4-111"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="eccb4-112">int</span><span class="sxs-lookup"><span data-stu-id="eccb4-112">int</span></span></p></td>
<td><p><span data-ttu-id="eccb4-113">Principale</span><span class="sxs-lookup"><span data-stu-id="eccb4-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="eccb4-114">Numero ID univoco che identifica questo tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="eccb4-114">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eccb4-115"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="eccb4-115"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="eccb4-116">int</span><span class="sxs-lookup"><span data-stu-id="eccb4-116">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eccb4-117">Codice di risposta SIP standard associato a questo errore.</span><span class="sxs-lookup"><span data-stu-id="eccb4-117">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eccb4-118"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="eccb4-118"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="eccb4-119">int</span><span class="sxs-lookup"><span data-stu-id="eccb4-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eccb4-120">ID diagnostica Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eccb4-120">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eccb4-121"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="eccb4-121"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="eccb4-122">Soglia</span><span class="sxs-lookup"><span data-stu-id="eccb4-122">Int</span></span></p></td>
<td><p><span data-ttu-id="eccb4-123">Stranieri</span><span class="sxs-lookup"><span data-stu-id="eccb4-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eccb4-124">Tipo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="eccb4-124">Type of the call.</span></span> <span data-ttu-id="eccb4-125">Per ulteriori informazioni, vedere la <a href="lync-server-2013-calltype-table.md">tabella CallType in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="eccb4-125">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eccb4-126"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="eccb4-126"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="eccb4-127">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="eccb4-127">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eccb4-128">Tipo della richiesta non riuscita.</span><span class="sxs-lookup"><span data-stu-id="eccb4-128">Type of request that failed.</span></span></p>
<p><span data-ttu-id="eccb4-129">Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="eccb4-129">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eccb4-130"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="eccb4-130"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="eccb4-131">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="eccb4-131">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eccb4-132">Tipo di contenuto della richiesta non riuscita.</span><span class="sxs-lookup"><span data-stu-id="eccb4-132">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="eccb4-133">Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="eccb4-133">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

