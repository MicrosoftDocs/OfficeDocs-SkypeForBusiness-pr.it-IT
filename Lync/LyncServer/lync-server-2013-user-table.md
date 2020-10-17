---
title: 'Lync Server 2013: tabella utente'
description: 'Lync Server 2013: tabella utente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15d1ac08a229f4afea35a2727ef1105a5f24b826
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558902"
---
# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="7a85f-103">Tabella user in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a85f-103">User table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a85f-104">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7a85f-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7a85f-p101">La tabella User è una tabella di supporto in cui è archiviato un elenco dei diversi utenti che hanno partecipato alle sessioni registrate nel database. Ogni record della tabella rappresenta un utente.</span><span class="sxs-lookup"><span data-stu-id="7a85f-p101">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7a85f-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="7a85f-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7a85f-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="7a85f-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7a85f-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="7a85f-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7a85f-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="7a85f-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a85f-111"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="7a85f-111"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="7a85f-112">int</span><span class="sxs-lookup"><span data-stu-id="7a85f-112">int</span></span></p></td>
<td><p><span data-ttu-id="7a85f-113">Principale</span><span class="sxs-lookup"><span data-stu-id="7a85f-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="7a85f-114">Numero univoco che identifica l'utente.</span><span class="sxs-lookup"><span data-stu-id="7a85f-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a85f-115"><strong>URI</strong></span><span class="sxs-lookup"><span data-stu-id="7a85f-115"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="7a85f-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7a85f-116">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7a85f-117">Univoco</span><span class="sxs-lookup"><span data-stu-id="7a85f-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="7a85f-118">Stringa URI.</span><span class="sxs-lookup"><span data-stu-id="7a85f-118">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a85f-119"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="7a85f-119"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="7a85f-120">int</span><span class="sxs-lookup"><span data-stu-id="7a85f-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a85f-121">1 è un tipo di URI sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7a85f-121">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="7a85f-122">2 è un URI utente.</span><span class="sxs-lookup"><span data-stu-id="7a85f-122">2 is user URI.</span></span></p>
<p><span data-ttu-id="7a85f-123">4 è un URI conferenza.</span><span class="sxs-lookup"><span data-stu-id="7a85f-123">4 is conference URI.</span></span></p>
<p><span data-ttu-id="7a85f-124">8 è un URI telefono.</span><span class="sxs-lookup"><span data-stu-id="7a85f-124">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a85f-125"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="7a85f-125"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="7a85f-126">int</span><span class="sxs-lookup"><span data-stu-id="7a85f-126">int</span></span></p></td>
<td><p><span data-ttu-id="7a85f-127">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7a85f-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7a85f-128">Tenant dell'utente, cui viene fatto riferimento dalla tabella Tenant.</span><span class="sxs-lookup"><span data-stu-id="7a85f-128">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a85f-129"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="7a85f-129"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7a85f-130">datetime</span><span class="sxs-lookup"><span data-stu-id="7a85f-130">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a85f-131">Ultimo indicatore di data e ora in cui si è verificata una chiamata audio di qualità scadente per l'utente.</span><span class="sxs-lookup"><span data-stu-id="7a85f-131">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a85f-132"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="7a85f-132"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="7a85f-133">datetime</span><span class="sxs-lookup"><span data-stu-id="7a85f-133">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a85f-134">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="7a85f-134">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

