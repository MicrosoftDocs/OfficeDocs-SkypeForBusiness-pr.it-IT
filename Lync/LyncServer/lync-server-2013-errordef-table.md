---
title: 'Lync Server 2013: tabella ErrorDef'
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
ms.openlocfilehash: c333017f122454d68bc452a5c183f8c09b6347a3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="217c4-102">Tabella ErrorDef in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="217c4-102">ErrorDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="217c4-103">_**Ultimo argomento modificato:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="217c4-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="217c4-104">Nella tabella ErrorDef vengono archiviate informazioni su ogni tipo di errore che può verificarsi.</span><span class="sxs-lookup"><span data-stu-id="217c4-104">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="217c4-105">Ogni record è un tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="217c4-105">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="217c4-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="217c4-106">Column</span></span></th>
<th><span data-ttu-id="217c4-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="217c4-107">Data Type</span></span></th>
<th><span data-ttu-id="217c4-108">Chiave/indice</span><span class="sxs-lookup"><span data-stu-id="217c4-108">Key/Index</span></span></th>
<th><span data-ttu-id="217c4-109">Dettagli</span><span class="sxs-lookup"><span data-stu-id="217c4-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="217c4-110"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="217c4-110"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="217c4-111">int</span><span class="sxs-lookup"><span data-stu-id="217c4-111">int</span></span></p></td>
<td><p><span data-ttu-id="217c4-112">Principale</span><span class="sxs-lookup"><span data-stu-id="217c4-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="217c4-113">Numero ID univoco che identifica questo tipo di errore.</span><span class="sxs-lookup"><span data-stu-id="217c4-113">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="217c4-114"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="217c4-114"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="217c4-115">int</span><span class="sxs-lookup"><span data-stu-id="217c4-115">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="217c4-116">Codice di risposta SIP standard associato a questo errore.</span><span class="sxs-lookup"><span data-stu-id="217c4-116">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="217c4-117"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="217c4-117"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="217c4-118">int</span><span class="sxs-lookup"><span data-stu-id="217c4-118">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="217c4-119">ID diagnostica Microsoft.</span><span class="sxs-lookup"><span data-stu-id="217c4-119">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="217c4-120"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="217c4-120"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="217c4-121">Soglia</span><span class="sxs-lookup"><span data-stu-id="217c4-121">Int</span></span></p></td>
<td><p><span data-ttu-id="217c4-122">Stranieri</span><span class="sxs-lookup"><span data-stu-id="217c4-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="217c4-123">Tipo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="217c4-123">Type of the call.</span></span> <span data-ttu-id="217c4-124">Per ulteriori informazioni, vedere la <a href="lync-server-2013-calltype-table.md">tabella CallType in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="217c4-124">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="217c4-125"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="217c4-125"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="217c4-126">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="217c4-126">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="217c4-127">Tipo della richiesta non riuscita.</span><span class="sxs-lookup"><span data-stu-id="217c4-127">Type of request that failed.</span></span></p>
<p><span data-ttu-id="217c4-128">Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="217c4-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="217c4-129"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="217c4-129"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="217c4-130">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="217c4-130">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="217c4-131">Tipo di contenuto della richiesta non riuscita.</span><span class="sxs-lookup"><span data-stu-id="217c4-131">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="217c4-132">Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="217c4-132">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

