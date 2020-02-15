---
title: 'Lync Server 2013: tabella endpoint'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 201e2ae3b44f59f0edb128f58af6c18e18e51931
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="573a4-102">Tabella endpoint in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="573a4-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="573a4-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="573a4-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="573a4-104">La tabella endpoint è una tabella di supporto in cui vengono archiviate informazioni sugli endpoint che hanno partecipato a sessioni registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="573a4-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="573a4-105">Ogni record nella tabella rappresenta un endpoint.</span><span class="sxs-lookup"><span data-stu-id="573a4-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="573a4-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="573a4-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="573a4-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="573a4-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="573a4-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="573a4-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="573a4-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="573a4-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="573a4-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="573a4-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="573a4-111">int</span><span class="sxs-lookup"><span data-stu-id="573a4-111">int</span></span></p></td>
<td><p><span data-ttu-id="573a4-112">Principale</span><span class="sxs-lookup"><span data-stu-id="573a4-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="573a4-113">Numero univoco che identifica l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="573a4-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="573a4-114"><strong>Nome</strong></span><span class="sxs-lookup"><span data-stu-id="573a4-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="573a4-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="573a4-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="573a4-116">Univoco</span><span class="sxs-lookup"><span data-stu-id="573a4-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="573a4-117">Nome dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="573a4-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="573a4-118"><strong>OS</strong></span><span class="sxs-lookup"><span data-stu-id="573a4-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="573a4-119">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="573a4-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="573a4-120">Sistema operativo (OS) dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="573a4-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="573a4-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="573a4-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="573a4-122">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="573a4-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="573a4-123">Nome della CPU dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="573a4-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="573a4-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="573a4-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="573a4-125">smallint</span><span class="sxs-lookup"><span data-stu-id="573a4-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="573a4-126">Numero di core della CPU dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="573a4-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="573a4-127"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="573a4-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="573a4-128">int</span><span class="sxs-lookup"><span data-stu-id="573a4-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="573a4-129">Velocità del processore della CPU dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="573a4-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="573a4-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="573a4-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="573a4-131">tinyint</span><span class="sxs-lookup"><span data-stu-id="573a4-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="573a4-132">Flag di bit che indica se il sistema è in esecuzione in un ambiente virtualizzato:</span><span class="sxs-lookup"><span data-stu-id="573a4-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="573a4-133">0x0000-None</span><span class="sxs-lookup"><span data-stu-id="573a4-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="573a4-134">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="573a4-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="573a4-135">0x0002 – VMWare</span><span class="sxs-lookup"><span data-stu-id="573a4-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="573a4-136">0x0004 – Virtual PC</span><span class="sxs-lookup"><span data-stu-id="573a4-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="573a4-137">0x0008 – Xen PC</span><span class="sxs-lookup"><span data-stu-id="573a4-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

